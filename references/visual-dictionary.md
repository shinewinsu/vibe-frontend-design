# Vibe Coding 视觉与结构全维词典 (Visual & Structural Encyclopedia)

> 本词典系统整合了 Adrian Punk（@AdrianPunk115）的《Vibe Coding 视觉词典（上/下篇）》、飞书/CSDN/知识猎人行业流通核心规范，以及 Linear/Vercel 等一线大厂的 Design Engineering 视觉架构标准。  
> 旨在提供**工业级、确定性、高精度**的专业 UI/UX 词汇体系与参数规范，彻底消除向 AI 提需求时的歧义。

---

## 目录
1. [布局形态规范 (Layout Patterns)](#1-布局形态规范-layout-patterns)
2. [页面纵向结构骨架 (Page Architecture & Flow)](#2-页面纵向结构骨架-page-architecture--flow)
3. [导航与路由体系 (Navigation Systems)](#3-导航与路由体系-navigation-systems)
4. [核心交互组件精解 (Interactive UI Components)](#4-核心交互组件精解-interactive-ui-components)
5. [五大现代视觉美学风格 (Visual Styles & Aesthetics)](#5-五大现代视觉美学风格-visual-styles--aesthetics)
6. [状态闭环与感知性能加载 (Feedback, States & Skeletons)](#6-状态闭环与感知性能加载-feedback-states--skeletons)
7. [设计令牌体系 (Design Tokens: Surfaces, Colors & Typography)](#7-设计令牌体系-design-tokens-surfaces-colors--typography)

---

## 1. 布局形态规范 (Layout Patterns)

### 1.1 Bento Grid（便当盒网格布局）
- **核心定义**：源自日本便当盒（Bento Box）与现代苹果/SaaS官网设计。通过不等大、不等高的圆角卡片矩阵组合，在一个视口内高密度、主次分明地呈现多元信息。
- **结构原则**：
  - **主角卡片 (Hero/Anchor Tile)**：占 2 列 2 行 (`col-span-2 row-span-2`) 或 3 列 2 行，承载最核心的可视化交互、实时图表或流程图。
  - **次要功能卡片 (Secondary Tiles)**：占 1 列 1 行或 2 列 1 行，展示指标、开关、微型代码块。
  - **间距与圆角**：统一使用 `gap-4` 或 `gap-6`，卡片圆角统一为 `rounded-2xl (16px)` 或 `rounded-xl (12px)`。
- **Tailwind 布局模板**：
  ```html
  <div class="grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-4 auto-rows-[240px]">
    <!-- 主角卡片 -->
    <div class="md:col-span-2 md:row-span-2 p-6 rounded-2xl bg-zinc-900/60 border border-white/10 relative overflow-hidden flex flex-col justify-between">
      <!-- 内部可视化插图与文案 -->
    </div>
    <!-- 指标副卡 -->
    <div class="md:col-span-1 md:row-span-1 p-5 rounded-2xl bg-zinc-900/40 border border-white/5 flex flex-col justify-between">
      <span class="text-xs font-semibold text-zinc-400 uppercase tracking-wider">Latency</span>
      <span class="text-3xl font-bold tracking-tight text-white">&lt; 8ms</span>
    </div>
    <!-- 宽型副卡 -->
    <div class="md:col-span-2 md:row-span-1 p-5 rounded-2xl bg-zinc-900/40 border border-white/5">
      <!-- 横向内容 -->
    </div>
  </div>
  ```

### 1.2 Split-Screen（分屏对决/对比布局）
- **核心定义**：将屏幕水平或垂直严格对半分割（50/50）或黄金分割（60/40、58/42）。一侧强调痛点、价值主张与强行动号召，另一侧承载交互体验、真实运行实例或视效。
- **视觉动线**：从左（或上）的理性陈述，平滑引导至右（或下）的感性具象演示。
- **Tailwind 布局模板**：
  ```html
  <section class="max-w-7xl mx-auto px-6 py-20 grid grid-cols-1 lg:grid-cols-12 gap-12 items-center">
    <div class="lg:col-span-5 space-y-6">
      <h1 class="text-5xl font-bold tracking-tight text-white leading-tight">...</h1>
      <p class="text-lg text-zinc-400 max-w-prose">...</p>
      <div class="flex items-center gap-4">...</div>
    </div>
    <div class="lg:col-span-7 relative rounded-2xl border border-white/10 bg-zinc-950 p-2 shadow-2xl">
      <!-- 交互式代码编辑器或运行预览 -->
    </div>
  </section>
  ```

### 1.3 Asymmetric 12-Column Grid（非对称十二栏排版）
- **核心定义**：打破机械对称，利用 12 栏弹性系统排布出 7:5、8:4 或带有错层负 Margin 的版面，赋予界面高级杂质感与动态呼吸感。
- **适用场景**：工作室作品集、高端消费硬件官网、前沿研究机构报告页。

### 1.4 Masonry Grid（错落瀑布流）
- **核心定义**：列宽固定、高度依据卡片内部内容（图片、长文摘录、评价内容）自然伸缩的错峰布局。
- **实现方案**：优先采用 CSS 原生 Multi-column 实现，性能极高且无计算抖动：
  ```html
  <div class="columns-1 sm:columns-2 lg:columns-3 gap-6 space-y-6">
    <div class="break-inside-avoid rounded-xl p-5 bg-zinc-900/40 border border-white/5">...</div>
  </div>
  ```

---

## 2. 页面纵向结构骨架 (Page Architecture & Flow)

顶级 Landing Page 严格遵循心智转化动线（Attention -> Interest -> Trust -> Action）：

### 2.1 Hero Section（主视觉首屏）
- **构成要素**：
  1. **Top Badge / Kicker**：小巧的药丸胶囊（Pill badge），展示版本更新或活动通知，带微小外发光与悬停箭头；
  2. **Display H1**：超大字号（48px - 72px），紧凑负字距（`-0.03em`），两行内讲透核心价值，首行高亮，次行微透；
  3. **Value Subtitle**：限制在 `60ch - 65ch` 行宽之内，正文灰调（`text-zinc-400`），绝不铺满全宽；
  4. **Dual CTA Group**：主行动点（高对比背景色 + 内微发光 + 物理按下手感） + 次行动点（幽灵线框 + 悬停微高亮）；
  5. **Interactive Preview Canvas**：真实产品 UI 截屏/交互式组件模型，置于透视角度或带有微弱光晕的基座上。

### 2.2 Social Proof（信任背书与 Logo 墙）
- **构成要素**：
  - 信任文案：“受到全球超过 5,000+ 工程师与团队的信赖”；
  - **Infinite Marquee**：无缝循环流动的半透明单色 Logo 跑马灯（使用 CSS `translateX` 硬件加速，悬停时自动暂停 `animation-play-state: paused`）。

### 2.3 Feature Deep-Dive & Playground（深度功能与互动游乐场）
- 采用 Tab 分类或分步骤 Stepper，用户点击左侧特性时，右侧联动切换对应的代码、动画或输出结果，给用户直接试用的控制感。

### 2.4 Testimonial Wall of Love（口碑评价墙）
- 真实用户头像、真实认证推文/评论结构、真实星星或认证标识，采用 Masonry 瀑布流排布。

### 2.5 Tiered Pricing Cards（分级定价卡片）
- 3 档配置（Starter / Pro / Enterprise）；
- **主角定价卡 (Recommended Card)**：必须在视觉上突出（外凸 4px、带渐变高光边框、顶部悬浮“最受欢迎 / 推荐”徽章、主色填充按钮）。

### 2.6 Accordion FAQ（手风琴问答区）
- 限制宽度在 `800px` 内，默认全部收起或展开第 1 项；采用高度平滑过渡，右侧图标从加号（+）顺滑旋转 45 度为乘号（×）。

---

## 3. 导航与路由体系 (Navigation Systems)

### 3.1 Sticky Frosted Glass Navbar（磨砂毛玻璃吸顶导航）
- **核心规格**：
  - 高度：`60px - 64px`；
  - 背景：`rgba(10, 11, 15, 0.75)`，配合 `backdrop-filter: blur(16px)` 与 `border-b border-white/[0.08]`；
  - 滚动感知：页面滚动超过 20px 时，通过 JS 切换为带有微弱阴影（`shadow-md shadow-black/20`）的加深状态。

### 3.2 Sliding Indicator Tabs（滑动滑块标签导航）
- **核心机制**：激活项的底部线条或胶囊背景不是生硬的高亮切换，而是随着用户点击平滑滑动至新位置。
- **推荐实现**：Framer Motion `layoutId="active-indicator"` 或基于 DOM `getBoundingClientRect()` 计算 `transform: translateX() scaleX()`。

### 3.3 Command Palette（CmdK 全局快捷指令面板）
- **灵感源**：Linear, Raycast, Vercel。
- **交互规范**：
  - 任意页面按下 `Cmd + K` 或 `Ctrl + K` 唤出；
  - 全屏半透明黑色蒙层 + 居中 600px 宽度弹窗；
  - 包含输入框（自动聚焦）、分类列表（Navigation, Actions, Themes）、键盘上下箭头选中高亮、回车执行、ESC 退出。

---

## 4. 核心交互组件精解 (Interactive UI Components)

### 4.1 Modal & Popover（模态对话框与浮层）
- **进入动画**：原点缩放扩散（`scale: 0.96 -> 1.0`, `opacity: 0 -> 1`），耗时 180ms，减速缓动。
- **退出动画**：`scale: 1.0 -> 0.98`, `opacity: 1 -> 0`，耗时 120ms（退出必须快于进入）。
- **层级焦点锁**：打开时页面禁止背景滚动（`overflow: hidden`），焦点自动捕获在弹窗内。

### 4.2 Stacked Toasts（堆叠式通知系统）
- 多条通知在右上角或底部居中弹出时，自动层叠计算：
  - 顶层：`scale(1.0) translateY(0)`
  - 第二层：`scale(0.95) translateY(10px) opacity(0.8)`
  - 第三层：`scale(0.90) translateY(20px) opacity(0.6)`
- 支持手势向外拖拽轻滑消除。

### 4.3 Segmented Control（分段选择器）
- 替代原生 Radio 单选组；
- 背景为深灰色胶囊条，内部选项为平级按钮，激活项带有纯白/亮色滑块底衬，配合弹性位移动效。

---

## 5. 五大现代视觉美学风格 (Visual Styles & Aesthetics)

### 5.1 Modern Clean SaaS (Linear-like Dark Mode)
- **基调**：深邃、克制、极度专注、暗调发光。
- **调色盘**：
  - Canvas: `#08090C`
  - Surface Level 1: `#101116`
  - Surface Level 2: `#171821`
  - Border: `rgba(255, 255, 255, 0.08)`
  - Border Hover: `rgba(255, 255, 255, 0.18)`
  - Text Primary: `#EDEDED`
  - Text Secondary: `#8A8F9E`
  - Text Muted: `#555964`
  - Accent: `#5E6AD2` (Linear Indigo) 或 `#3B82F6` (Electric Blue)
- **核心质感**：1px 细微发光内边框（Inner Border）、微弱径向漫反射光晕（Subtle Ambient Glow）。

### 5.2 Swiss International Editorial（瑞士平面杂志风）
- **基调**：典雅、高知、艺术留白、排版冲击力。
- **调色盘**：
  - Canvas: `#F9F9F8` (暖羊皮纸白)
  - Text: `#121212` (沉实炭黑)
  - Accent: `#0029FF` (国际克莱因蓝) 或 `#E63946` (瑞士红)
- **核心质感**：大幅衬线体（Playfair, Newsreader）与精准几何无衬线混排、网格裁切线、极大字阶跨度、零多余阴影。

### 5.3 Glassmorphism 2.0（深色次世代毛玻璃）
- **核心质感**：
  ```css
  background: rgba(18, 19, 26, 0.65);
  backdrop-filter: blur(20px) saturate(180%);
  -webkit-backdrop-filter: blur(20px) saturate(180%);
  border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.4), inset 0 1px 0 0 rgba(255, 255, 255, 0.1);
  ```

### 5.4 Neo-Brutalism（新粗野主义）
- **核心质感**：
  - 纯黑外描边：`border: 2.5px solid #000000;`
  - 硬投影：`box-shadow: 5px 5px 0px 0px #000000;`（悬停时位移并缩小投影：`translate(2px, 2px)` + `box-shadow: 3px 3px 0px #000`）
  - 色彩搭配：荧光黄 `#FDFF00`、赛博绿 `#00F5A0`、亮紫色 `#B388FF`。

### 5.5 High-Trust Enterprise B2B（可信现代企业风）
- **核心质感**：清爽高对比浅色体系（`#FFFFFF` 卡片浮于 `#F8FAFC` 底板）、`4.5:1` 以上严格 WCAG AA 文本对比、严谨层级阴影（Tailwind `shadow-sm` / `shadow-md`）。

---

## 6. 状态闭环与感知性能加载 (Feedback, States & Skeletons)

### 6.1 Shimmering Skeleton Screen（高光波纹骨架屏）
- **规范**：骨架块必须与最终渲染卡片在宽高、内边距、行数上完全一致（1:1 结构复刻），杜绝布局偏移（Cumulative Layout Shift, CLS = 0）。
- **纯 CSS 渐变波纹实现**：
  ```css
  @keyframes shimmer {
    0% { transform: translateX(-100%); }
    100% { transform: translateX(100%); }
  }
  .skeleton {
    position: relative;
    overflow: hidden;
    background-color: rgba(255, 255, 255, 0.05);
    border-radius: 8px;
  }
  .skeleton::after {
    position: absolute;
    top: 0; right: 0; bottom: 0; left: 0;
    transform: translateX(-100%);
    background-image: linear-gradient(
      90deg,
      rgba(255, 255, 255, 0) 0,
      rgba(255, 255, 255, 0.06) 20%,
      rgba(255, 255, 255, 0.12) 60%,
      rgba(255, 255, 255, 0)
    );
    animation: shimmer 1.6s infinite;
    content: '';
  }
  ```

### 6.2 Progressive Blur-up Image Loading（渐进模糊加载）
- 图片初始加载展示微缩低清图或统一颜色占位，叠加 `filter: blur(16px)`；高清图加载完成触发 `onLoad`，平滑 300ms 去除模糊。

### 6.3 Empty States（有价值的空状态）
- 包含 3 样东西：
  1. 结构化图标或插图；
  2. 诚实的标题与一句话原因说明；
  3. 主要引导动作（CTA），直接把用户带回主路径（例如：“暂无项目数据，立即创建第一个项目 →”）。

---

## 7. 设计令牌体系 (Design Tokens: Surfaces, Colors & Typography)

### 7.1 表面层级令牌 (Surfaces Hierarchy)
```css
:root {
  --canvas: #090a0f;       /* Level 0: 视口最底色 */
  --surface-1: #111218;    /* Level 1: 大区块容器、侧边栏底色 */
  --surface-2: #181922;    /* Level 2: Bento 卡片底色、列表项 */
  --surface-elevated: #20222e; /* Level 3: 模态窗、下拉菜单、浮动面板 */
  
  --border-subtle: rgba(255, 255, 255, 0.06);
  --border-strong: rgba(255, 255, 255, 0.14);
  --border-hover: rgba(255, 255, 255, 0.24);

  --ink-primary: #ededed;
  --ink-secondary: #a1a1aa;
  --ink-muted: #71717a;
  --ink-faint: #3f3f46;
}
```

### 7.2 模块化字阶表 (Modular Typography Scale - 1.25)
| 级别 | 字号 (px / rem) | 行高 (Leading) | 字距 (Tracking) | 适用场景 |
|---|---|---|---|---|
| **Display Mega** | `64px / 4.0rem` | `1.05` | `-0.035em` | Hero 主大标题 |
| **Heading 1** | `40px / 2.5rem` | `1.15` | `-0.025em` | 页面一级标题 |
| **Heading 2** | `32px / 2.0rem` | `1.20` | `-0.02em` | 板块/区块标题 |
| **Heading 3** | `24px / 1.5rem` | `1.25` | `-0.015em` | Bento 卡片标题 |
| **Heading 4** | `18px / 1.125rem`| `1.35` | `-0.01em` | 小分组、列表项标题 |
| **Body Base** | `15px / 0.9375rem`| `1.60` | `0` | 标准正文内容 |
| **Caption** | `13px / 0.8125rem`| `1.50` | `0.01em` | 辅助说明、时间戳 |
| **Overline/Badge**| `11px / 0.6875rem`| `1.00` | `0.06em` (Uppercase) | 标签徽章、顶标 |
