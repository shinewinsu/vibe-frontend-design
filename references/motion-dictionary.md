# Vibe Coding 网页动效与物理微交互全维词典 (Motion & Physics Encyclopedia)

> 本词典系统整合了 Adrian Punk（@AdrianPunk115）的《Vibe Coding 网页动效词典（上/中/下篇）》、Emil Kowalski 的《Animations on the Web (animations.dev)》、Rauno Freiberg 的《Invisible Details of Interaction Design》以及 Paco Coursey 的手艺（Craft）工程哲学。  
> 旨在提供**工业级、物理级、高性能**的动效描述语言与现成代码算法，彻底根除“加点丝滑动效”等模糊指令，实现丝滑、克制、物理真实的现代交互体验。

---

## 目录
1. [动效四层拆解法则 (The 4-Layer Motion Framework)](#1-动效四层拆解法则-the-4-layer-motion-framework)
2. [基础显现与进入节奏 (Entrance & Reveal Rhythms)](#2-基础显现与进入节奏-entrance--reveal-rhythms)
3. [多层视差滚动与粘性钉扎 (Parallax Scrolling & Sticky Pinning)](#3-多层视差滚动与粘性钉扎-parallax-scrolling--sticky-pinning)
4. [磁吸按钮物理建模 (Magnetic Button Physics)](#4-磁吸按钮物理建模-magnetic-button-physics)
5. [光标跟随与卡片局部聚光灯 (Cursor Follower & Card Spotlight)](#5-光标跟随与卡片局部聚光灯-cursor-follower--card-spotlight)
6. [组件微交互与形状演进 (Component Feedback & Morphing)](#6-组件微交互与形状演进-component-feedback--morphing)
7. [FLIP 布局补间与视图转场 (FLIP Transitions & View Transitions API)](#7-flip-布局补间与视图转场-flip-transitions--view-transitions-api)
8. [物理曲线数学与硬件加速铁律 (Easing, Performance & a11y)](#8-物理曲线数学与硬件加速铁律-easing-performance--a11y)

---

## 1. 动效四层拆解法则 (The 4-Layer Motion Framework)

向 AI 描述任何动效时，必须按照以下四层结构给出明确参数：

```
┌────────────────────────────────────────────────────────┐
│ 1. 触发源 (Trigger)                                    │
│    └─ 谁在什么时机发起动作？(Hover / In-view / Scroll / Click)│
├────────────────────────────────────────────────────────┤
│ 2. 运动主体与变换属性 (Actor & Animated Properties)   │
│    └─ 哪个容器变动？改的是 opacity, translateY, scale, 还是 clip? │
├────────────────────────────────────────────────────────┤
│ 3. 缓动曲线与终态收敛 (Physics, Easing & Settling)      │
│    └─ 弹簧参数 (stiffness, damping) 还是减速曲线 (cubic-bezier)?   │
├────────────────────────────────────────────────────────┤
│ 4. 边界约束与无障碍 (UX Guardrails & a11y)             │
│    └─ 触屏降级方案？是否强制尊重 prefers-reduced-motion?     │
└────────────────────────────────────────────────────────┘
```

---

## 2. 基础显现与进入节奏 (Entrance & Reveal Rhythms)

### 2.1 Stagger Cascade Reveal（交错级联上浮）
- **核心原理**：同组卡片或列表项如果同时淡入，会显得生硬机械；采用交错延迟（Stagger），第一张卡片先动，随后每张卡片以固定毫秒微小偏移递进，形成视觉波浪。
- **参数标准**：
  - 子项位移：`translateY(16px -> 0)` 或 `translateY(24px -> 0)`；
  - 不透明度：`opacity: 0 -> 1`；
  - 级联间隔（Stagger Interval）：`50ms - 80ms`（超过 100ms 会显得拖沓缓慢，低于 30ms 视觉无法分辨）；
  - 缓动曲线：`cubic-bezier(0.16, 1, 0.3, 1)`，单项持续时间 `400ms`。
- **Framer Motion 实现**：
  ```tsx
  const containerVariants = {
    hidden: { opacity: 0 },
    visible: {
      opacity: 1,
      transition: { staggerChildren: 0.06, delayChildren: 0.1 }
    }
  };

  const itemVariants = {
    hidden: { opacity: 0, y: 20 },
    visible: {
      opacity: 1,
      y: 0,
      transition: { duration: 0.4, ease: [0.16, 1, 0.3, 1] }
    }
  };
  ```

### 2.2 Blur-to-Clear Reveal（由虚入实渐现）
- **核心原理**：结合高斯模糊滤镜与透明度，元素由虚淡变为清晰实体，极具现代前沿科技感。
- **参数标准**：
  - 初始态：`filter: blur(12px); opacity: 0; transform: scale(0.98);`
  - 终末态：`filter: blur(0px); opacity: 1; transform: scale(1.0);`
  - 持续时间：`400ms - 500ms`。

### 2.3 Line & Word Split Reveal（文字掩码拆分滑出）
- **核心原理**：常见于顶级作品集与品牌发布页大标题。大标题外层包裹 `overflow: hidden` 的掩码容器，文字拆解为单行或单词，从下方垂直滑入，犹如精密打印。
- **CSS 原生规范**：
  ```css
  .split-line-wrapper {
    overflow: hidden;
  }
  .split-line-text {
    transform: translateY(100%);
    animation: splitReveal 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards;
  }
  @keyframes splitReveal {
    to { transform: translateY(0); }
  }
  ```

---

## 3. 多层视差滚动与粘性钉扎 (Parallax Scrolling & Sticky Pinning)

### 3.1 Multi-layer Differential Rates（分层差速滚动）
- **物理机制**：随着用户纵向滚动视口，不同深度的图层以不同倍率移动：
  - **背景网格 / 环境光晕层 (Background)**：速率 `0.2x - 0.4x`（慢速后退，营造宏大远景空间）；
  - **核心内容与文本层 (Midground)**：速率 `1.0x`（正常页面滚动，保证阅读平稳）；
  - **浮动点缀与指标徽章 (Foreground/Floating)**：速率 `1.3x - 1.5x`（快速上浮掠过视线）。
- **Framer Motion 实现范式**：
  ```tsx
  import { useScroll, useTransform, motion } from "framer-motion";
  import { useRef } from "react";

  export function ParallaxHero() {
    const ref = useRef(null);
    const { scrollYProgress } = useScroll({ target: ref, offset: ["start start", "end start"] });

    const yBackground = useTransform(scrollYProgress, [0, 1], ["0%", "30%"]);
    const yForeground = useTransform(scrollYProgress, [0, 1], ["0%", "-50%"]);

    return (
      <section ref={ref} className="relative h-[120vh] overflow-hidden">
        <motion.div style={{ y: yBackground }} className="absolute inset-0 bg-grid-pattern opacity-20 will-change-transform" />
        <div className="relative z-10 max-w-4xl mx-auto pt-32">...</div>
        <motion.div style={{ y: yForeground }} className="absolute top-1/2 right-10 p-4 rounded-xl glass-card will-change-transform">
           99.9% Uptime
        </motion.div>
      </section>
    );
  }
  ```

### 3.2 Sticky Pinning & Scale-down（吸顶钉扎缩小）
- 当一个全屏视觉画板滚动到顶部边缘时，将其 `position: sticky; top: 0` 钉住固定；随着继续滚动，画板随着进度按比例由 `scale: 1.0` 缩小为 `0.92`，四周留出留白，下一区块平滑盖上来。

---

## 4. 磁吸按钮物理建模 (Magnetic Button Physics)

### 4.1 物理交互机理
- **感应半径 (Influence Radius)**：以按钮几何中心为圆心，外扩为按钮本身宽度的 `1.5` 倍到 `2.0` 倍形成无形重力场；
- **距离衰减与最大位移**：光标越靠近中心，吸引力越强，但按钮整体位移限制在阈值内（如外层最大 `14px`）；
- **内外双层视差 (Double-layer Parallax)**：外框移动较小（如 12px），按钮内部的文字和图标移动较大（如 20px），形成流体般的张力感；
- **释放回弹 (Release Spring)**：鼠标移出感应区后，触发弹簧振荡平滑复位，杜绝生硬闪回。

### 4.2 生产级 React + Framer Motion 实现
```tsx
import React, { useRef, useState } from "react";
import { motion } from "framer-motion";

export function MagneticButton({ children, className = "" }: { children: React.ReactNode; className?: string }) {
  const ref = useRef<HTMLButtonElement>(null);
  const [position, setPosition] = useState({ x: 0, y: 0 });

  const handleMouseMove = (e: React.MouseEvent<HTMLButtonElement>) => {
    if (!ref.current) return;
    const { clientX, clientY } = e;
    const { left, top, width, height } = ref.current.getBoundingClientRect();
    const centerX = left + width / 2;
    const centerY = top + height / 2;

    // 计算鼠标距离中心的相对偏移向量，并以 0.35 阻尼缩放
    const deltaX = (clientX - centerX) * 0.35;
    const deltaY = (clientY - centerY) * 0.35;
    setPosition({ x: deltaX, y: deltaY });
  };

  const handleMouseLeave = () => {
    setPosition({ x: 0, y: 0 });
  };

  return (
    <motion.button
      ref={ref}
      onMouseMove={handleMouseMove}
      onMouseLeave={handleMouseLeave}
      animate={{ x: position.x, y: position.y }}
      transition={{ type: "spring", stiffness: 180, damping: 14, mass: 0.1 }}
      className={`relative inline-flex items-center justify-center select-none active:scale-[0.98] ${className}`}
    >
      <motion.span
        animate={{ x: position.x * 0.4, y: position.y * 0.4 }}
        transition={{ type: "spring", stiffness: 200, damping: 15 }}
        className="inline-flex items-center gap-2 pointer-events-none"
      >
        {children}
      </motion.span>
    </motion.button>
  );
}
```

---

## 5. 光标跟随与卡片局部聚光灯 (Cursor Follower & Card Spotlight)

### 5.1 自定义光标跟随圈 (Smooth Cursor Follower)
- **规格**：
  - 尺寸：直径 `32px`，无背景填充，`1.5px` 细白描边；
  - 属性：强制设置 `pointer-events: none`（绝对禁止阻挡用户真实点击！）；
  - 混合模式：`mix-blend-mode: difference`（在白底上自动变黑，黑底上自动变白）；
  - 悬停变形：当鼠标移动至 `<a>` 链接或可交互按钮上时，跟随圈平滑放大至 `64px`，背景填充轻微半透明白（`rgba(255,255,255,0.15)`），离开后弹性还原；
  - 移动端：通过 `@media (pointer: coarse)` 强制 `display: none`。

### 5.2 卡片表面动态聚光灯 (Card Spotlight Hover)
- **实现原理**：在 Bento 卡片内部，利用 CSS 变量 `--mouse-x` 和 `--mouse-y` 记录光标在当前卡片中的相对像素位置，动态渲染跟随的径向渐变。
```tsx
import React, { useRef } from "react";

export function SpotlightCard({ children, className = "" }: { children: React.ReactNode; className?: string }) {
  const cardRef = useRef<HTMLDivElement>(null);

  const handleMouseMove = (e: React.MouseEvent<HTMLDivElement>) => {
    if (!cardRef.current) return;
    const rect = cardRef.current.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;
    cardRef.current.style.setProperty("--mouse-x", `${x}px`);
    cardRef.current.style.setProperty("--mouse-y", `${y}px`);
  };

  return (
    <div
      ref={cardRef}
      onMouseMove={handleMouseMove}
      className={`group relative rounded-2xl bg-zinc-900/60 p-6 border border-white/10 overflow-hidden ${className}`}
    >
      {/* 聚光灯光晕层 */}
      <div
        className="pointer-events-none absolute -inset-px rounded-2xl opacity-0 transition-opacity duration-300 group-hover:opacity-100"
        style={{
          background: `radial-gradient(500px circle at var(--mouse-x, 0) var(--mouse-y, 0), rgba(255, 255, 255, 0.08), transparent 80%)`,
        }}
      />
      <div className="relative z-10">{children}</div>
    </div>
  );
}
```

---

## 6. 组件微交互与形状演进 (Component Feedback & Morphing)

### 6.1 Origin-Aware Modal Transitions（原点感知弹窗）
- 依据 Emil Kowalski 的原则：弹窗或菜单应从**触发它的按钮位置**开始展开，而不是无缘无故从屏幕中心炸开。
- 进场：`scale: 0.95 -> 1.0` + `opacity: 0 -> 1`（200ms ease-out）；
- 退场：`scale: 1.0 -> 0.97` + `opacity: 1 -> 0`（140ms ease-in）；
- 背景蒙层：`backdrop-filter: blur(8px) brightness(60%)` 伴随同步淡入淡出。

### 6.2 Morphing State Button（变形状态按钮）
- 点击提交后，按钮保持原中心点不变，左右两端向中心收缩变成一个直径等于原高度的圆（如 `h-10 w-36 -> h-10 w-10`），同时文字渐隐，中心浮现 16px 圆形 Spinner。
- 异步完成后，Spinner 演变为打勾图标（Checkmark），背景变为墨绿色，保持 1.2 秒后平滑展开复原。

---

## 7. FLIP 布局补间与视图转场 (FLIP Transitions & View Transitions API)

### 7.1 FLIP 原理重排（First, Last, Invert, Play）
- **解决痛点**：在对卡片列表进行分类筛选或增删时，避免元素凭空消失或瞬移卡顿。
- **机制**：
  1. **First**：记录卡片初始坐标 `getBoundingClientRect()`；
  2. **Last**：改变 DOM 状态，记录卡片终末坐标；
  3. **Invert**：使用 `transform: translate(dx, dy)` 将卡片瞬间反向贴回旧位置；
  4. **Play**：清除 transform 并应用缓动补间，让卡片平滑滑入新槽位。
- 在 React 中直接使用 Framer Motion 的 `layout` 属性即可自动触发零成本的 FLIP 补间：
  ```tsx
  <motion.div layout transition={{ type: "spring", stiffness: 350, damping: 30 }} className="card">
    ...
  </motion.div>
  ```

### 7.2 Native View Transitions API（现代跨页面平滑过渡）
- 现代浏览器原生支持的页面视图平滑衔接：
  ```javascript
  if (document.startViewTransition) {
    document.startViewTransition(() => {
      // 更新 DOM 或切换路由
      renderNewPageContent();
    });
  } else {
    renderNewPageContent();
  }
  ```

---

## 8. 物理曲线数学与硬件加速铁律 (Easing, Performance & a11y)

### 8.1 黄金缓动曲线速查
- **通用优雅减速 (Natural Decel - 适用于入场与悬停)**：
  `cubic-bezier(0.16, 1, 0.3, 1)`（超平滑减速，启动极快，刹车极其丝滑）。
- **干脆退出加速 (Snappy Exit - 适用于弹窗关闭、元素移除)**：
  `cubic-bezier(0.4, 0, 1, 1)` 或 `duration: 150ms ease-in`（退出必须快于进入！）。
- **自然物理弹簧 (Physical Spring - 适用于卡片重排、磁吸、Tab 滑块)**：
  `stiffness: 150 - 220`, `damping: 14 - 18`, `mass: 0.1 - 0.2`（干脆自然，微弱回弹，无眩晕晃荡）。

### 8.2 GPU 合成与防抖原则
1. **只对两大属性施加动画**：严格限制动效在 **`transform`** 和 **`opacity`** 上运行！避免对 `width`, `height`, `top`, `margin`, `padding` 进行动画，防止触发浏览器的 Layout Thrashing（重排重绘）。
2. **硬件加速标记**：对视差图层或高频位移元素加上 `will-change: transform` 或 `transform: translate3d(0, 0, 0)`。

### 8.3 无障碍防线 (prefers-reduced-motion)
在所有全局样式或动效库中，必须强制声明防眩晕降级：
```css
@media (prefers-reduced-motion: reduce) {
  *, ::before, ::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```
