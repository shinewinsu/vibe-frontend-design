# 前端设计工程自动化走查与排错指南 (Design Engineering QA & Debugging)

> 本指南整合了 Adrian Punk（@AdrianPunk115）的《Loop Engineering 自动化循环迭代》、《CSS 层叠上下文排查》实战，以及现代前端性能与可访问性审查的刚性标准。  
> 专为解决现代前端开发中“样式层级错乱（z-index 战争）”、“滚动布局重排（Layout Thrashing）”、“移动端莫名横滑”与“组件未覆盖异常态”等硬核工程暗坑。

---

## 目录
1. [CSS z-index 层叠上下文排查矩阵](#1-css-z-index-层叠上下文排查矩阵)
2. [防布局抖动铁律 (Zero CLS Architecture)](#2-防布局抖动铁律-zero-cls-architecture)
3. [GPU 硬件加速与渲染管线审查](#3-gpu-硬件加速与渲染管线审查)
4. [高频事件节流与状态机防抖](#4-高频事件节流与状态机防抖)
5. [跨端响应式“零溢出”走查清单](#5-跨端响应式零溢出走查清单)

---

## 1. CSS z-index 层叠上下文排查矩阵

### 1.1 常见的 z-index 失效根因
很多开发者遇到元素被遮挡时，习惯盲目加到 `z-[99999]`，结果依旧被遮挡。这是因为**层叠上下文（Stacking Context）被父级限制了**！

**以下属性会悄悄创建新的独立层叠上下文**：
1. `opacity` 小于 1；
2. `transform`、`filter`、`backdrop-filter`、`perspective` 不为 `none`；
3. `will-change` 指定了上述任一属性；
4. `contain: paint` 或 `contain: layout`。

一旦父容器建立了新的层叠上下文，子元素内部哪怕写 `z-index: 999999`，在外部看来其层级最高也只能等于该父容器在上一层上下文中的层级！

### 1.2 全局规范分层阶梯 (The Z-Index Scale)
系统严禁随手乱写数值，必须统一锁死在设计令牌中：
```css
:root {
  --z-base:       0;     /* 普通文档流卡片与内容 */
  --z-sticky:     10;    /* 粘性表头、吸顶侧边小工具 */
  --z-fixed-nav:  40;    /* 全局吸顶毛玻璃导航 Navbar */
  --z-drawer:     50;    /* 抽屉侧滑面板 Drawer */
  --z-modal-bg:   60;    /* 模态弹窗半透明暗色蒙层 */
  --z-modal:      70;    /* 模态弹窗本体 Dialog */
  --z-popover:    80;    /* 浮动下拉菜单、Tooltip、气泡 */
  --z-toast:      90;    /* 全局悬浮通知 Toast */
  --z-cursor:     100;   /* 自定义鼠标跟随器 */
}
```

---

## 2. 防布局抖动铁律 (Zero CLS Architecture)

累积布局偏移（CLS）是导致页面“廉价感”和“手滑误触”的头号杀手：

### 2.1 预防布局偏移黄金法则
1. **所有图片和视频必须显式标注 `width` 和 `height`，或容器声明 `aspect-ratio`**：
   ```html
   <div class="aspect-video w-full rounded-xl overflow-hidden bg-zinc-900">
     <img src="..." loading="lazy" decoding="async" class="w-full h-full object-cover" />
   </div>
   ```
2. **异步加载区必须预留 1:1 高度骨架屏**：
   数据未返回时，列表卡片容器必须渲染高度相同的 Skeleton 占位，杜绝数据返回瞬间把下方内容猛然挤下去。
3. **字体加载无闪烁 (Font Display: Swap + Fallback Metric)**：
   使用 Next.js `next/font`，自动匹配系统后备字体的尺寸指标（Size Adjust, Ascent, Descent），防止字体加载时文字重新折行跳跃。

---

## 3. GPU 硬件加速与渲染管线审查

### 3.1 杜绝 Layout Thrashing（强制同步布局）
- **禁止在动画或高频滚动事件中交替读取与修改 DOM 几何属性**（如循环调用 `offsetWidth`、`scrollHeight`、`getComputedStyle()`）；
- **动画属性只允许两兄弟**：
  - [OK] **`transform`** (`translate3d`, `scale`, `rotate`)
  - [OK] **`opacity`**
- [X] **严禁动画属性**：`width`, `height`, `top`, `left`, `margin`, `padding`（会触发全页面重排 Reflow）。

---

## 4. 高频事件节流与状态机防抖

### 4.1 滚动与鼠标移动事件处理
- 在监听 `window.onscroll` 或卡片 `onMouseMove` 时：
  - 必须使用 `requestAnimationFrame`（rAF）或 `useMotionValue` 进行调度；
  - 避免在事件回调中进行大量复杂数学计算或触发 React `setState`，使用原生 CSS 变量注入（`style.setProperty`）绕过 React 重新渲染开销。

---

## 5. 跨端响应式“零溢出”走查清单

在交付代码前，必须在 3 个严苛视口下进行物理走查：

1. **390px（iPhone 典型移动端）**：
   - 检查横向滚动条是否彻底消失（`document.documentElement.scrollWidth === window.innerWidth`）；
   - 检查所有可点击按钮/链接的高度是否达到 `44px` 最小无障碍触摸标准；
   - 检查固定在底部的操作栏是否为虚拟 Home 键预留了安全区域（`padding-bottom: env(safe-area-inset-bottom)`）。
2. **768px（iPad / 平板视口）**：
   - 检查 Bento Grid 是否平滑退化为合理的 2 列；
   - 检查分屏（Split-screen）是否由左右排列转换为上下流式排列。
3. **1440px+（桌面高分大屏）**：
   - 检查主容器是否配置了最大宽度约束（如 `max-w-7xl mx-auto`），防止内容散漫无边。
