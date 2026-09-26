---
name: vibe-frontend-design
description: 顶级前端设计与交互工程全能 Skill。深度融合 Adrian Punk 的《Vibe Coding 视觉词典》（布局/结构/导航/组件/视觉风格/加载反馈）、《Vibe Coding 网页动效词典》（基础动效/视差滚动/磁吸按钮/鼠标跟随/组件反馈/布局过渡/页面转场）及《AI网站前端设计工作流》，结合开源社区顶流 taste-skill 的 Anti-Slop 防模板化法则、Linear/Vercel 级 Design Engineering 工艺标准、模块化排版系统与物理弹簧动效。在设计、构建、重构任何网页、Landing Page、Web 应用或复杂动效时使用。
---

# Vibe Frontend Design & Craft Skill
> **“把模糊的审美感觉，转化为 AI 与浏览器能 100% 精确执行的确定性工程资产。”**
> 本 Skill 专治各种“AI 模板味”、“紫色渐变球”、“无脑三等分对称卡片”、“生硬跳变动效”与“只会说高级一点却做不出质感”的痛点。

---

## 目录与模块化参考库
- [0. 核心设计诊断与三档旋钮 (Design Read & The Three Dials)](#0-核心设计诊断与三档旋钮-design-read--the-three-dials)
- [1. 网页骨架与布局词典 (Layout & Page Architecture)](#1-网页骨架与布局词典-layout--page-architecture)
- [2. 视觉风格与设计工程学 (Visual Aesthetics & Design Engineering)](#2-视觉风格与设计工程学-visual-aesthetics--design-engineering)
- [3. 网页动效词典与物理动量 (Motion & Micro-interactions Dictionary)](#3-网页动效词典与物理动量-motion--micro-interactions-dictionary)
- [4. AI 网站前端设计工作流 (End-to-End Vibe Coding Workflow)](#4-ai-网站前端设计工作流-end-to-end-vibe-coding-workflow)
- [5. 即插即用的 Vibe Coding 提示词模板库 (Prompt Cookbook)](#5-即插即用的-vibe-coding-提示词模板库-prompt-cookbook)
- [6. 交付自检清单与无障碍刚性红线 (Pre-flight Quality Gate & Accessibility)](#6-交付自检清单与无障碍刚性红线-pre-flight-quality-gate--accessibility)

### 专项深入模块手册 (Modular Reference Manuals)
当需要查阅完整参数、底层数学模型与真实代码实现时，随时读取本 Skill 对应的专项手册：
- 📖 [**视觉词典全书 (Visual Dictionary)**](references/visual-dictionary.md)：全套布局卡片、结构流、5大风格与设计令牌。
- 🎬 [**动效与物理全书 (Motion Dictionary)**](references/motion-dictionary.md)：四层动效法则、多层视差、磁吸按钮物理、FLIP 重排。
- 💻 [**生产级工业代码配方库 (Code Recipes)**](references/code-recipes.md)：12 套即插即用 React + Tailwind + Framer Motion 生产代码（磁吸、聚光灯、3D 卡片、光束边框、解密文字等）。
- ⭐ [**GitHub 高星前端生态全景 (High-Star Ecosystem)**](references/github-highstar-ecosystem.md)：shadcn/ui、Magic UI、Aceternity UI、React Bits (48k★)、ibelick、vaul、sonner、cmdk 底层架构与公式。
- 📝 [**提示词任务书模版库 (Prompt Cookbook)**](references/prompt-cookbook.md)：八字段任务书框架与全行业实战 Prompt。
- 🀄 [**中文字体与现代排版指南 (Chinese Typography)**](references/chinese-typography.md)：中文字阶黄金律、中西文盘古中间隙、大标题负字距与标点避头尾。
- 🏛️ [**档案美学与平铺静物体系 (Archive Aesthetic & Knolling)**](references/archive-aesthetic.md)：瑞士国际排版、正交坐标系、漫反射柔光、标本元件化。
- 🛠️ [**设计工程自动化走查与排错 (Design Engineering QA)**](references/design-engineering-qa.md)：CSS z-index 层叠上下文排查、CLS=0 布局防抖、GPU 硬件加速与跨端走查。

---

## 0. 核心设计诊断与三档旋钮 (Design Read & The Three Dials)

### 0.A Design Read（强制设计定调，拒绝跳步）
在动手写第一行 HTML/CSS/Tailwind 或构思组件之前，**必须先输出一行“设计定调 (Design Read)”**，彻底封死 AI 默认模板的退路：

> **`Design Read: 正在构建 [页面类型] 面向 [目标受众]，采用 [核心视觉风格] 视觉语言，设定旋钮 [V=? / M=? / D=?]，技术栈倾向于 [设计系统 / 组件库 / 动效库]。`**

*示例*：
- `Design Read: 正在构建 AI 开发者工具 Landing Page 面向 技术架构师与独立开发者，采用 Linear 风格暗调极简 视觉语言，设定旋钮 [V=7 / M=6 / D=4]，技术栈倾向于 Tailwind CSS + Lucide Icons + Framer Motion 弹簧微交互。`
- `Design Read: 正在构建 创意设计工作室作品集 面向 顶尖品牌总监与投资人，采用 瑞士杂志编排 (Swiss Editorial) 视觉语言，设定旋钮 [V=9 / M=8 / D=3]，技术栈倾向于 原生 CSS Grid + 视差滚动 + View Transitions API。`

---

### 0.B 三档旋钮系统 (The Three Dials)
根据 Design Read 的场景需求，动态锁定三大参数基准：
1. **`DESIGN_VARIANCE` (设计变化率 / 意料之外度：1 - 10)**
   - `1-3`：严谨对称、企业级中庸、政府/金融/合规优先（极简对齐）。
   - `4-6`：现代商业 SaaS、品牌官网（规整中包含局部不对称与打破边界）。
   - `7-8`：消费级爆款产品、Apple 风格体验（Bento Grid、视差差速、多维留白）。
   - `9-10`：Awwwards 获奖级、创意工作室、潮牌实验（激进不对称、排版碰撞、全屏视差）。
2. **`MOTION_INTENSITY` (动效烈度：1 - 10)**
   - `1-2`：近乎纯静态，仅保留按键轻微颜色过渡（严谨管理后台）。
   - `3-4`：克制优雅，仅保留进入视口微位移（12-16px）与平滑悬停。
   - `5-7`：标准现代网页，视差差速、磁吸按钮、卡片微发光跟随、Tab 滑动指示器。
   - `8-10`：电影级流体物理、3D 透视倾斜、跟随光标反色变异、全屏共享元素变形。
3. **`VISUAL_DENSITY` (信息密度：1 - 10)**
   - `1-3`：艺术画廊式极高留白、巨大字阶对比（奢侈品、高端硬件、作品集）。
   - `4-5`：黄金标准 Landing Page、内容博客、产品介绍页。
   - `6-8`：生产力应用、SaaS 核心工作区、多维看板（Linear / GitHub 仪表盘）。
   - `9-10`：专业交易终端、数据监控中心（Bloomberg / 飞机驾驶舱）。

---

### 0.C Anti-Slop（防 AI 模板化死刑清单）
**严禁出现以下 10 种典型的“AI 偷懒套话式设计”**：
1. ❌ **严禁千篇一律的 AI 紫色/蓝粉放射渐变发光球（Mesh Gradient Blobs）**。
2. ❌ **严禁无脑的三等分对称卡片阵列（3-Column Feature Cards）**，强制采用 Bento Grid 或 5:7 / 8:4 不对称比例。
3. ❌ **严禁深色模式直接使用纯黑（#000000）配纯白（#ffffff）文字**，必须使用带色温的炭黑底色（如 `#090a0f`, `#0d0e12`）与多层灰色文字（`text-zinc-100`, `text-zinc-400`）。
4. ❌ **严禁所有元素无脑应用 Glassmorphism（毛玻璃）**，毛玻璃只能用于浮动导航或悬浮卡片，不可全屏糊满。
5. ❌ **严禁所有元素以相同的节奏、方向和速度同时淡入**，必须有先导（Lead）与交错级联（Stagger，50-80ms 递进）。
6. ❌ **严禁按钮点击时没有任何物理下按反馈（Missing Active State）**，必须支持 `active:scale-[0.98]`。
7. ❌ **严禁页面出现水平横向滚动条（Horizontal Overflow）**。
8. ❌ **严禁使用未调整字距（Letter-spacing）的大标题**，现代无衬线大标题必须设置负字距（`tracking-tight`，`-0.02em` 至 `-0.03em`）。
9. ❌ **严禁无反馈的空白加载态**，必须有骨架屏（带 Shimmer 高光波纹）或状态保持。
10. ❌ **严禁假装有动效却忽略 `prefers-reduced-motion`**。

---

## 1. 网页骨架与布局词典 (Layout & Page Architecture)

### 1.A 五大现代布局形态（Layout）
| 布局形态 | 核心特点与结构构成 | 适用场景 | 关键 CSS / Tailwind 实现范式 |
|---|---|---|---|
| **Bento Grid<br>(便当盒网格)** | 大小不一、高低错落的圆角矩形卡片组合；包含 1 个横跨两列的“主角卡片（Hero Tile）”与若干次要功能卡片，主次层次极强。 | SaaS 核心功能展示、产品能力全景、控制台仪表盘 | `grid grid-cols-1 md:grid-cols-3 gap-4 lg:grid-cols-4`<br>主角卡：`col-span-2 row-span-2` |
| **Split-screen<br>(分屏对决/对比)** | 50/50 或 60/40 强视觉分割；左侧为高强度价值主张文案与 CTA，右侧为动态交互组件、真实 UI 截图或代码编辑器。 | Landing Page 首屏、代码与效果实时预览、双模式对比 | `grid grid-cols-1 lg:grid-cols-12`<br>文案区 `lg:col-span-5`，预览区 `lg:col-span-7` |
| **Asymmetric 12-Col<br>(不对称十二栏系统)** | 打破传统中轴对称，利用 12 栏系统进行 7:5、8:4 或带有负向 Margin 偏移的重叠排版，营造杂志级现代呼吸感。 | 品牌官网、高端硬件产品页、设计工作室 | `grid grid-cols-12 gap-6`<br>配合 `-mt-12` 或 `translate-y-8` 产生轻度层级遮挡 |
| **Masonry<br>(错落瀑布流)** | 等宽不等高，卡片自然依据内部内容高度向下排列，空间利用率极高且富有生机。 | 客户评价墙、社区动态、图片灵感集、设计素材展示 | `columns-1 sm:columns-2 lg:columns-3 gap-6 space-y-6` |
| **Card Flow<br>(卡片信息流/时间轴)** | 纵向单列或微双列对齐，带左侧或中间的发光连线与节点指示器，强调时序或执行步骤。 | 产品迭代 Changelog、操作指引 Step-by-Step、活动时间线 | `relative border-l border-zinc-800 pl-6 space-y-8`，节点：`absolute -left-1.5` |

---

### 1.B 经典页面全景结构流水线（Page Structure）
一个专业的 Landing Page 必须具备节奏分明的纵向骨架：
```
┌────────────────────────────────────────────────────────┐
│ 1. Sticky Frosted Navbar (Brand Logo + Nav + Action)   │
├────────────────────────────────────────────────────────┤
│ 2. Hero Section (Tag Badge + Mega H1 + Sub + Dual CTA) │
│    └─ Interactive Live Preview / 3D Product Demo Canvas │
├────────────────────────────────────────────────────────┤
│ 3. Social Proof (Infinite Marquee Logos / Trust Metric)│
├────────────────────────────────────────────────────────┤
│ 4. Bento Grid Features (Core Value Proposition)        │
├────────────────────────────────────────────────────────┤
│ 5. Deep Dive / Interactive Playground (Tabbed Demo)    │
├────────────────────────────────────────────────────────┤
│ 6. Social Testimonials (Masonry Wall of Love)          │
├────────────────────────────────────────────────────────┤
│ 7. Transparent Pricing (Tiered Cards + Recommended Tag)│
├────────────────────────────────────────────────────────┤
│ 8. Accordion FAQ (Expandable with Auto-height)         │
├────────────────────────────────────────────────────────┤
│ 9. High-impact Final CTA Box                           │
├────────────────────────────────────────────────────────┤
│ 10. Multi-column Footer (Links + Status + Switcher)    │
└────────────────────────────────────────────────────────┘
```

---

### 1.C 导航体系（Navigation）
- **Sticky Frosted Navbar（毛玻璃吸顶导航）**：
  - 核心属性：`position: sticky; top: 0; backdrop-filter: blur(16px); background: rgba(..., 0.75); border-bottom: 1px solid rgba(..., 0.1); z-index: 50;`
  - 细节：向下滚动超过 20px 时，自动增加更清晰的底边阴影或微发光。
- **Sliding Tabs Indicator（平滑滑动标签栏）**：
  - 核心属性：激活标签底部跟随一个物理滑动的胶囊背景或指示横条，使用 Framer Motion 的 `layoutId="active-tab"` 实现无缝位移，绝对不用瞬间闪烁切换。
- **Slide-over Drawer（抽屉式侧滑面板）**：
  - 移动端导航与复杂详情检查的核心容器，右侧/底部带回弹物理滑入，伴随半透明暗色遮罩（Backdrop Fade）。
- **Command Palette（⌘K 全局搜索与指令面板）**：
  - 居中悬浮、高斯模糊遮罩、键盘上下键焦点导航、分类 Group（常用功能、跳转、帮助）、回车即刻执行。

---

### 1.D 核心交互组件（Common Components）
- **Modal / Dialog（模态弹窗）**：
  - 打开机制：从触发点或屏幕中心，以 `scale: 0.95 -> 1.0` 叠加 `opacity: 0 -> 1` 平滑弹出，耗时 200ms。
  - 关闭机制：`ESC` 键响应、点击外部遮罩关闭、右上角显式关闭按钮。
- **Stacked Toast System（堆叠通知系统）**：
  - 右上角或底部居中弹出；多条消息时自动折叠为 3D 景深堆叠（第二条缩小 5% 并向下微偏，第三条缩小 10%）；支持手势右滑消除。
- **Smart Forms & Inputs（智能表单）**：
  - 悬浮标签（Floating Label）或清晰的上方小标题；
  - 聚焦时高亮外光圈：`ring-2 ring-primary/20 border-primary`；
  - 错误态红线与平滑展开的 Helper Text；禁用态明确置灰且阻断点击。

---

## 2. 视觉风格与设计工程学 (Visual Aesthetics & Design Engineering)

### 2.A 五大主流现代视觉风格解构
1. **Modern Minimal / Linear-like SaaS（极简暗调科技风）**：
   - **调色板**：底色 `#08090c`、卡片面 `#111218`、悬停面 `#181922`、边框 `#232533`、点缀色（霓虹蓝 `#3b82f6` 或电光紫 `#6366f1`）。
   - **特征**：1px 细微发光边框（Subtle Inner Border）、卡片内微弱径向渐变光晕（Ambient Glow）、无衬线字体（Geist / Inter）、文字透明度阶梯（100% -> 60% -> 40%）。
2. **Swiss Editorial / Modern Magazine（瑞士杂志平面风）**：
   - **调色板**：纯净高白 `#fbfbfb` 配高对比近黑 `#111111`、点缀单色（如国际克莱因蓝、国际红）。
   - **特征**：大幅衬线主标题（Newsreader / Playfair Display）搭配冷酷几何无衬线说明文、不对称栅格、大面积极致留白、强排版标点。
3. **Glassmorphism 2.0（现代毛玻璃）**：
   - **特征**：摒弃初代劣质发白毛玻璃，现代采用深色多重模糊：`backdrop-blur-md bg-white/[0.03] border border-white/[0.08] shadow-[0_8px_32px_0_rgba(0,0,0,0.36)]`。
4. **Neo-Brutalism（新粗野主义）**：
   - **特征**：纯黑粗边框（`2px` 或 `3px solid #000`）、硬投影（`box-shadow: 4px 4px 0px #000`，无羽化模糊）、高饱和度对比纯色（柠檬黄、亮绿、电光粉）、几何形状硬贴合。
5. **Clean Enterprise B2B（现代可信企业风）**：
   - **特征**：浅灰底色（`#f8fafc`）、纯白高洁卡片（`#ffffff`）、柔和多层阴影（Tailwind `shadow-sm` 至 `shadow-md`）、沉稳海军蓝（`#0f172a`）、WCAG AAA 级高对比度。

---

### 2.B 表面层级系统 (Surface Hierarchy & Lighting)
不要让所有元素处于同一平面！构建四层物理表面：
- **Level 0 (Canvas)**：页面基底色（如 `#09090b`）。
- **Level 1 (Surface)**：大结构容器、侧边栏、网格卡片底（如 `#121216`，边框 `rgba(255,255,255,0.08)`）。
- **Level 2 (Overlay / Card)**：悬浮组件、交互项、列表卡片（如 `#1a1a22`，悬停时产生内外发光）。
- **Level 3 (Elevated / Modal)**：模态弹窗、下拉菜单、浮动气泡（带深层阴影 `shadow-2xl` 与独立聚焦轮廓）。

---

### 2.C 排版工程学 (Typography Engineering)
1. **模块化字阶 (Modular Scale 1.25 / 1.333)**：
   - Display / Hero: `48px - 72px` (Line-height: 1.05 - 1.1, Letter-spacing: `-0.03em`)
   - H1: `36px - 40px` (Line-height: 1.15, Letter-spacing: `-0.025em`)
   - H2: `28px - 32px` (Line-height: 1.2, Letter-spacing: `-0.02em`)
   - H3: `20px - 24px` (Line-height: 1.3, Letter-spacing: `-0.015em`)
   - Body Large: `18px` (Line-height: 1.5, Letter-spacing: `-0.01em`)
   - Body Base: `15px - 16px` (Line-height: 1.6, Letter-spacing: `0`)
   - Caption / Small: `13px - 14px` (Line-height: 1.5, Letter-spacing: `0.01em`)
   - Overline / Badge: `11px - 12px` (Font-weight: 600, Text-transform: uppercase, Letter-spacing: `0.05em`)
2. **正文舒适宽度 (Measure)**：文本段落最大宽度严格控制在 `60ch - 75ch`（约 540px - 680px），超过此宽度必须分栏，禁止单行文字跨满 1920px 屏幕！
3. **中西文标点避头尾**：强制设置 `break-words text-pretty`，大标题避免孤字孤词折行。

---

## 3. 网页动效词典与物理动量 (Motion & Micro-interactions Dictionary)

### 3.A 动效“四层拆解法则” (The 4-Layer Motion Framework)
在向 AI 提出动效需求时，严禁使用“帮我加点酷炫动效”，必须按四层规范输出：
1. **触发机制 (Trigger)**：`Hover`（鼠标悬停）、`On-mount`（初始化加载）、`In-view`（滚动进入视口阈值 0.2）、`Scroll Progress`（滚动百分比 0-100%）、`Click/Tap`（点击激活）。
2. **运动对象与属性 (Actor & Properties)**：明确哪个容器、哪行文字位移；改变的是 `opacity`、`transform: translateY`、`scale` 还是 `clip-path`。
3. **缓动物理与终态 (Physics, Easing & Settling)**：
   - 机械界面：`cubic-bezier(0.16, 1, 0.3, 1)`（超顺滑减速曲线，快速启动、平滑刹车）。
   - 弹性界面：`type: "spring", stiffness: 150, damping: 15`（弹性自然回弹，无生硬震荡）。
4. **UX 约束与无障碍 (UX Guardrails & a11y)**：
   - 强制响应式断点：触屏设备（`pointer: coarse`）禁用鼠标跟随与微小悬停；
   - 强制遵守 `@media (prefers-reduced-motion: reduce)`，自动将所有位移淡化为即时切换。

---

### 3.B 基础出现动效 (Entrance & Reveal)
- **Stagger Cascade Reveal（交错级联上浮）**：
  - 容器内 N 个卡片，不是一起猛现，而是以 `staggerChildren: 0.06`（每张卡片延迟 60ms）依次从 `y: 20, opacity: 0` 过渡到 `y: 0, opacity: 1`。
- **Blur-to-Clear Reveal（由虚入实渐现）**：
  - 文字或卡片从 `filter: blur(12px); opacity: 0; scale: 0.98` 在 400ms 内平滑过渡为 `blur(0); opacity: 1; scale: 1`，具有极高科技质感。
- **Line / Word Split Reveal（逐行/逐字显现）**：
  - 大标题拆分为行或单词，置于 `overflow: hidden` 的掩码容器中，文字从下方 `translateY(100%)` 顺滑滑入，如报刊印刷般利落。

---

### 3.C 页面视差与指针交互 (Parallax & Pointer Dynamics)
- **Multi-layer Parallax Scrolling（多层差速视差）**：
  - 背景网格/装饰光晕移动速率：`0.3x`
  - 正文与主要容器移动速率：`1.0x`
  - 前景浮动卡片/图标移动速率：`1.3x - 1.5x`
  - 形成天然景深空间，配合 GPU 加速 `transform: translate3d(0, y, 0)`。
- **Magnetic Button（磁吸按钮）**：
  - 感应区：外层包围盒尺寸为按钮本体的 `1.5x`；
  - 偏移量：外层按钮根据光标距离中心向量产生最大 `12px - 15px` 的跟随位移；
  - 双层视差：按钮内部文字与箭头产生额外 `20px` 的同向位移；
  - 回弹物理：鼠标离开感应区后，触发弹簧震荡复位（`stiffness: 200, damping: 12`）。
- **Cursor Follower & Spotlight Glow（光标跟随与卡片局部聚光灯）**：
  - 卡片表面监听 `onMouseMove`，动态计算相对百分比坐标 `(x%, y%)`；
  - 在卡片内渲染一个绝对定位的径向渐变跟随圆斑：
    `background: radial-gradient(400px circle at var(--mouse-x) var(--mouse-y), rgba(255,255,255,0.06), transparent 80%)`；
  - 鼠标移动到哪，卡片边缘和内表面就在哪里泛出微光。

---

### 3.D 组件微交互与形变 (Micro-interactions & Layout Morphing)
- **Morphing Submit Button（变形反馈按钮）**：
  - 点击前：宽矩形文案按钮；
  - 加载中：两端平滑收缩为圆形，文字淡出，中心浮现 16px Spinner；
  - 成功：Spinner 淡出，绿色 Checkmark 划线展开，保持 1.5 秒后平滑复位。
- **FLIP-based Grid Reordering（FLIP 布局平滑重排）**：
  - 当用户点击筛选标签（如按分类过滤卡片）时，保留的卡片平滑滑移到新槽位，被过滤卡片 `scale: 0.9 + fade-out`，新卡片顺序浮现，杜绝任何生硬跳变。
- **Pure CSS Auto-height Accordion（纯 CSS 自适应高度手风琴）**：
  ```css
  .accordion-content {
    display: grid;
    grid-template-rows: 0fr;
    transition: grid-template-rows 250ms cubic-bezier(0.16, 1, 0.3, 1);
  }
  .accordion-item[data-open="true"] .accordion-content {
    grid-template-rows: 1fr;
  }
  .accordion-inner {
    overflow: hidden;
  }
  ```

---

## 4. AI 网站前端设计工作流 (End-to-End Vibe Coding Workflow)

### 阶段 1：需求工程与架构梳理（Micro-briefing）
1. 明确目标受众与核心转化路径（Conversion Funnel）；
2. 梳理一屏一件事的信息架构（Information Architecture），列出 5-7 个核心区块的明确顺序；
3. 输出 **Part 0.A 的 Design Read** 与 **0.B 的 Three Dials 参数**。

### 阶段 2：设计系统与视觉原子（Design Tokens First）
1. **色彩系统**：定义 Canvas, Surface, Border, Primary, Text-Primary, Text-Muted 的具体 CSS 变量或 Tailwind 映射；
2. **字体阶梯**：配置好 Heading 字体、Body 字体、等宽 Code 字体，锁定负字距规则；
3. **圆角与光影规范**：全局统一基准圆角（如卡片 `rounded-xl: 12px`，按钮 `rounded-lg: 8px`，徽章 `rounded-full`）。

### 阶段 3：结构优先编码（Skeleton & Layout Generation）
1. 先写无装饰的纯结构布局（Bento Grid、Split Screen 栅格比例）；
2. 填充高保真真实文案（绝不使用 Lorem ipsum 假字，真实文案才能看出折行节奏）；
3. 检查 1280px / 768px / 390px 三端流式自适应，确保无横向滚动条。

### 阶段 4：动效注入与物理调校（Motion & Micro-interactions）
1. 添加视口滚动级联进入动效（In-view Stagger）；
2. 为核心 CTA 配置磁吸（Magnetic）或按下缩放（Active Scale）；
3. 为 Bento 卡片挂载光标光斑（Spotlight Hover）；
4. 补充骨架屏与空状态过渡。

### 阶段 5：工程化交付自检（Pre-flight Quality Check）
1. 检查键盘 Tab 导航焦点可见性（Focus Ring）；
2. 检查系统深色/浅色偏好与 `prefers-reduced-motion` 适配；
3. 检查移动端触摸区域 $\ge 44\times 44\text{px}$。

---

## 5. 即插即用的 Vibe Coding 提示词模板库 (Prompt Cookbook)

### 模版 1：旗舰级 SaaS Landing Page 结构提示词
```markdown
请你扮演资深设计工程师（Design Engineer）。为我们开发一个世界级的 B2B AI 工具落地页首屏与核心特性区。

【设计定调 (Design Read)】
- 页面定位：面向开发者与技术总监的高性能 AI 代理工作台
- 视觉风格：Linear 风格暗调极简（Modern Dark Minimal），拒绝 AI 默认紫色渐变球
- 旋钮参数：DESIGN_VARIANCE: 7, MOTION_INTENSITY: 6, VISUAL_DENSITY: 5
- 技术栈：Next.js App Router + Tailwind CSS + Lucide Icons + Framer Motion

【布局与结构要求】
1. Sticky Navbar：磨砂半透明吸顶（backdrop-blur-md），左侧 Logo，中间为功能/文档/定价锚点，右侧为“登录”与发光主 CTA。
2. Hero Section：
   - 顶部药丸型徽章：“v2.0 现已发布：支持多代理并行调度 →”；
   - 标题：大字阶紧凑负字距（tracking-tight），64px 粗体，第一行纯白，第二行微渐变近白；
   - 价值副标：最大宽度 65ch，灰调 text-zinc-400，解释核心价值；
   - 双 CTA 按钮组：主按钮“免费开始使用”（内发光 + active 物理按下反馈），次按钮“查看架构白皮书”（带边框）；
   - 产品画布：Hero 下方展示一个高保真可交互的终端模拟器/看板界面（带有真实的节点连接连线与代码高亮，带有浅浅的 3D 悬停透视感）。
3. Bento Grid 特性区：采用 4 列不等大便当盒布局：
   - 卡片 1（主角卡，跨 2 列 2 行）：核心可视化流程图，带循环脉冲光效；
   - 卡片 2（跨 2 列 1 行）：实时性能对比图表（清晰的数据刻度与极高对比度）；
   - 卡片 3、4：微型指标卡片，包含代码片段与毫秒级延迟徽章。

【工程质量与细节】
- 所有卡片背景使用 #111218，边框为 1px 细线 border-white/[0.08]，内部带有根据鼠标坐标移动的局部径向微发光（Spotlight）；
- 响应式处理：在 390px 移动端优雅折叠为单列流，无任何横向溢出；
- 动效适配 @media (prefers-reduced-motion: reduce)。
```

---

### 模版 2：多层视差滚动与磁吸按钮注入提示词
```markdown
请为当前页面的产品展示板块注入高阶视效与指针交互：

1. 视差滚动（Parallax Scrolling）：
   - 使用 Framer Motion 的 useScroll 和 useTransform 监听视口滚动；
   - 背景装饰网格位移速率设为 0.3x，形成深层景深；
   - 核心图文卡片按 1.0x 正常滚动；
   - 浮动指标胶囊（如“99.9% 可用性”、“<10ms 延迟”）以 1.4x 差速快速上浮；
   - 移动端或触摸设备自动降级为静态平铺，避免卡顿。

2. 磁吸按钮（Magnetic CTA）：
   - 将主行动点封装为磁吸组件：感应外框为按钮尺寸 1.5 倍；
   - 鼠标进入感应区后，按钮向光标方向平滑偏移最大 14px，内部文字产生 20px 视差微位移；
   - 离开后通过弹簧物理（stiffness: 160, damping: 14）自然回弹复位；
   - 适配 pointer: coarse，移动端触摸屏幕时直接禁用计算。
```

---

### 模版 3：状态完整闭环与骨架屏提示词
```markdown
请完善当前数据看板模块的全状态闭环（Loading, Empty, Error, Settled）：

1. 加载态（Loading State）：
   - 禁止使用全屏居中的普通 Spinner；
   - 提供与真实列表卡片 1:1 轮廓对应的骨架屏（Skeleton），带有 1.5 秒从左至右扫过的渐变高光波纹（Shimmer 动画）。
2. 空状态（Empty State）：
   - 当接口返回 items 为空时，展示结构化空状态：
   - 居中展示带有虚线外框的极简插画图标、明确的引导标题、两句解释说明，以及主 CTA 按钮“立即创建第一个工作流”。
3. 异常态（Error State）：
   - 包含故障原因友好说明、错误码徽章，以及一个带有物理反馈的“重新加载”重试按钮。
4. 内容切换过渡：从骨架屏切换到真实内容时，应用 250ms 的平滑交叉淡化（Cross-fade），避免视觉闪烁。
```

---

## 6. 交付自检清单与无障碍刚性红线 (Pre-flight Quality Gate & Accessibility)

任何前端页面或组件产出前，必须自查以下 12 项指标：

| 校验维度 | 检查项 | 验收标准 | 违规现象 / 修复建议 |
|---|---|---|---|
| **排版与层次** | 标题字距 (Tracking) | 大标题设置负字距（`-0.02em`） | 大标题字间距散漫松垮 ➔ 加 `tracking-tight` |
| **排版与层次** | 行长约束 (Measure) | 正文单行宽度在 60-75ch 之间 | 一行字从屏幕最左跨到最右 ➔ 加 `max-w-prose` |
| **色彩与光影** | 表面对比度 (Contrast) | 关键文本对比度符合 WCAG AA ($\ge 4.5:1$) | 暗色底上灰色字看不清 ➔ 调亮中性色阶 |
| **色彩与光影** | 表面层次 (Surfaces) | 区分底色、卡片面色、浮层色 | 页面一片死平 ➔ 引入 Level 0/1/2 分层 |
| **交互与手感** | 点击反馈 (Press State) | 按钮具备 active 物理缩放 | 点击毫无反应 ➔ 加 `active:scale-[0.98]` |
| **交互与手感** | 键盘聚焦 (Focus Ring) | 键盘导航具备可见高亮轮廓 | 无障碍审查报错 ➔ 加 `focus-visible:ring-2` |
| **动效与过渡** | 节奏级联 (Stagger) | 列表/卡片错峰递进出现 | 所有卡片同一瞬间生硬闪现 ➔ 加 50ms 级联 |
| **动效与过渡** | 缓动曲线 (Easing) | 采用物理弹簧或顺滑减速曲线 | 机械匀速线性运动 ➔ 改用 `cubic-bezier(0.16,1,0.3,1)` |
| **无障碍防线** | 动效减弱偏好 | 适配 `prefers-reduced-motion` | 晕动症用户抗议 ➔ 在媒体查询中将位移动画降级为淡入 |
| **移动端适配** | 触摸热区 (Touch Target)| 按钮与链接可点击区域 $\ge 44\times 44\text{px}$ | 手机上按不到 ➔ 增加内边距 `p-3` |
| **移动端适配** | 溢出检测 (No Overflow)| 任何视口下均无水平横向滚动条 | 页面左右晃荡 ➔ 检查绝对定位或负 margin 元素 |
| **状态闭环** | 异常与骨架屏覆盖 | 拥有完整 Loading / Empty / Error 态 | 数据加载时页面白屏或跳动 ➔ 加 Shimmer 骨架屏 |
