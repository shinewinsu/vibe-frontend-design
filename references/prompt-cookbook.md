# Vibe Coding 提示词工程任务书终极模版库 (Prompt Cookbook)

> 本模版库基于《从视觉词典到可执行任务》的 **八字段任务书方法论**，结合 GitHub 爆款 prompt 实践，将所有视觉与动效词典沉淀为**可以直接复制、按需填空、交付给 AI（Claude Code / Cursor / Codex 等）执行的工业级提示词**。

---

## 目录
1. [八字段任务书核心架构规范](#1-八字段任务书核心架构规范)
2. [旗舰级 SaaS 官网全案任务书模版](#2-旗舰级-saas-官网全案任务书模版)
3. [开发者 / 设计师顶尖作品集任务书模版](#3-开发者--设计师顶尖作品集任务书模版)
4. [生产力应用与控制台仪表盘任务书模版](#4-生产力应用与控制台仪表盘任务书模版)
5. [专项动效与微交互定向注入模版集](#5-专项动效与微交互定向注入模版集)
6. [老旧丑陋网页重构与去 AI 油腻感审计模版](#6-老旧丑陋网页重构与去-ai-油腻感审计模版)

---

## 1. 八字段任务书核心架构规范

向 AI 下发任何前端需求时，严格杜绝一句两句模糊聊天，必须以结构化任务书组织输入：

```markdown
# 1. 角色 (Role)
明确 Agent 承担的复合角色（如“兼任信息架构师、UI 设计师与资深前端工程师”），并要求分步确认结构后再写代码。

# 2. 核心目标 (Goal)
页面为谁解决什么核心痛点，整个页面最首要的单一转化动作 (CTA) 是什么。

# 3. 目标受众与认知 (Audience)
用户的设备倾向（桌面宽屏 / 移动手机优先）、专业背景、心智模型。

# 4. 页面结构与区块清单 (Pages & Blocks)
URL 路由规划，以及从上至下的清晰 Section 列表。

# 5. 信息架构与视觉动线 (Information Architecture)
F 型或 Z 型视觉动线，主次信息的排布逻辑与内容权重。

# 6. 视觉系统与设计规范 (Design System & Dials)
调用视觉词典中的确定性参数：调色板、字阶、间距、容器约束，以及三档旋钮参数设定。

# 7. 交互行为与状态机 (Interactions & States)
组件的 Hover、Active、Focus 状态，加载中、骨架屏、空状态与异常处理。

# 8. 技术栈与验收标准 (Tech & Acceptance Criteria)
依赖库、零布局偏移 (CLS=0)、无横向滚动条、无障碍规范与多端走查要求。
```

---

## 2. 旗舰级 SaaS 官网全案任务书模版

```markdown
# Role & Process
你是一位具有顶级审美追求的资深设计工程师（Design Engineer），精通现代 Web 前端开发与微交互物理动量。
请先输出页面组件树、区块层级和状态清单，等待我的确认；确认后再输出完整的可运行代码。

# Design Read & Dials
- Design Read: 正在构建 AI 智能体开发平台 Landing Page 面向 高阶全栈工程师与架构师，采用 Linear 风格暗调极简（Modern Dark Minimalist）视觉语言，技术栈倾向于 Next.js App Router + Tailwind CSS + Lucide Icons + Framer Motion。
- 旋钮配置：DESIGN_VARIANCE: 7, MOTION_INTENSITY: 6, VISUAL_DENSITY: 5。
- 严禁行为：严禁出现紫色发光大球、无脑三等分对称卡片、无字距调节的大标题、缺少点击物理反馈的按钮。

# Layout & Page Flow
1. Sticky Navbar：磨砂半透明吸顶（backdrop-blur-md bg-zinc-950/70 border-b border-white/5），左侧 Brand Logo，中间导航锚点，右侧“文档”与发光 CTA “开始使用”。
2. Hero Section：
   - 顶部药丸徽章：“SignalEngine 3.0 正式发布：亚毫秒级分布式事件流 →”；
   - 标题：负字距紧凑无衬线字体（tracking-tight），64px，第一行“驯服海量噪声”，第二行微透灰“捕获最纯粹的机器智能信号”；
   - 价值副标：最大宽度 62ch，text-zinc-400，解释核心技术指标；
   - 双 CTA 按钮组：主按钮“立即免费接入”（带内发光与 active:scale-[0.98] 手感），次按钮“查看基准测试报告”；
   - 产品画布：Hero 下方展示一个高保真交互式工作台预览卡片，包含代码流、实时吞吐仪表盘与状态指示灯。
3. Social Proof：无缝循环流动的半透明单色 Logo 跑马灯（Marquee），悬停时自动平滑暂停。
4. Bento Grid 核心特性：4 列错落便当盒网格：
   - 卡片 1（主角卡，跨 2 列 2 行）：实时流拓扑可视化，带脉冲信号点；
   - 卡片 2（跨 2 列 1 行）：多维度延迟对比柱状图；
   - 卡片 3、4：微型终端代码块与审计合规证明。
5. Tiered Pricing：3 档定价卡片，中间 Pro 档凸起 4px 并带有微渐变发光外框。
6. Accordion FAQ：手风琴问答，平滑 CSS Grid 高度自适应，加号图标展开顺滑旋转 45 度。
7. Footer：多列结构化索引、版权信息、系统运行状态点（绿色脉冲灯）。

# Visual & Motion Details
- 背景使用 #08090C，表面使用 #101116，卡片使用 #171821，边框统一为 1px 细线 border-white/[0.08]；
- Bento 卡片内集成光标相对坐标驱动的局部径向渐变聚光灯效果（Spotlight）；
- 主 CTA 按钮增加磁吸物理回弹（Magnetic Button）；
- 动效适配 @media (prefers-reduced-motion: reduce)。

# Acceptance Criteria
1. 在 1440px 桌面、768px 平板和 390px 移动端均流式自适应，严禁任何水平横向滚动条；
2. 移动端触摸区域全部不小于 44x44px；
3. 文本对比度严格通过 WCAG AA (>= 4.5:1)。
```

---

## 3. 开发者 / 设计师顶尖作品集任务书模版

```markdown
# Role & Objective
扮演精通瑞士国际平面设计风格与现代 Web 交互的前端艺术家。
为一位全栈独立开发者/设计工程师构建一个具有个人辨识度、极致质感与高传播度的个人作品集首页。

# Design Read & Dials
- Design Read: 正在构建 个人作品集/数字花园 面向 顶尖海外科技公司创始人与工程副总裁，采用 瑞士杂志排版 (Swiss Editorial) 遇上 极简现代代码 的视觉语言，技术栈倾向于 原生 CSS + Tailwind + View Transitions。
- 旋钮配置：DESIGN_VARIANCE: 9, MOTION_INTENSITY: 7, VISUAL_DENSITY: 4。

# Key Sections & Structure
1. 非对称 Hero：
   - 巨大字阶衬线体（Newsreader / Playfair）排版：“Crafting software at the intersection of design & systems.”；
   - 右侧或下方点缀极简实时状态卡（包含本地时间 CST、当前正在开发的项目动态）。
2. 代表作精选 (Featured Work)：
   - 摒弃常规卡片，采用类似画廊目录的大列表排版；
   - 鼠标悬停列表某一行时，对应项目的预览截图在光标侧方以平滑缓动浮现跟随（Hover Preview Thumbnail）。
3. 开源与手艺实验 (Lab & Experiments)：
   - 展示 4 个精巧的微交互原型（包含磁吸组件、自适应折叠、物理滑块）。
4. 思考与写作 (Essays)：
   - 极简单列文章列表，带阅读时长与发布时间戳。
5. 极简页脚：一键复制邮件地址按钮（点击后原处平滑演变为“已复制到剪贴板！”打勾反馈）。

# Craft Rules
- 默认采用暖白纸质底色 (#F9F9F8) 配炭黑 (#121212) 文字，支持快捷键切换为纯净暗色模式；
- 大标题增加逐字滑入动效（Split text reveal）；
- 鼠标滚轮滑动时配合轻微的视差差速滚动。
```

---

## 4. 生产力应用与控制台仪表盘任务书模版

```markdown
# Role & Scope
扮演具有十年复杂企业软件架构经验的资深前端工程师。
为专业数据分析系统构建一个高密度、低认知负荷、响应迅捷的监控看板主视图。

# Design Read & Dials
- Design Read: 正在构建 实时数据流监控控制台 面向 运维工程师与 SRE 专家，采用 Linear/Vercel 暗调控制台 视觉语言，技术栈使用 React + Tailwind + Radix UI Primitives。
- 旋钮配置：DESIGN_VARIANCE: 3, MOTION_INTENSITY: 3, VISUAL_DENSITY: 8。

# Layout Architecture
1. 可折叠紧凑侧边栏（Collapsible Sidebar）：图标 + 文字，支持快捷键 [ 收起为仅图标模式。
2. 顶部状态条：包含工作区选择器、全局健康指示灯（绿/黄/红呼吸灯）、⌘K 搜索触发器。
3. 主监控画布：
   - 顶部 KPI 快速概览行：4 个紧凑指标卡片（包含核心数值、环比趋势小箭头、微型 Sparkline 迷你走势线）；
   - 中间实时数据流大表格：支持列宽拖拽、多列排序、状态标签、固定表头（Sticky Header）；
   - 数据加载期提供 1:1 对应的 Shimmer 骨架屏占位。
4. 全面支持键盘驱动交互：J/K 上下选择数据行，回车在侧滑抽屉（Slide-over Drawer）中展开详情。
```

---

## 5. 专项动效与微交互定向注入模版集

### 5.1 磁吸按钮 (Magnetic Button) 注入模版
```markdown
请将当前页面的 [CTA 按钮选择器] 改造为物理磁吸按钮：
1. 监听外层容器的 mousemove 事件，检测光标相对按钮中心的位移向量 (dx, dy)；
2. 当光标处于按钮半径 1.5 倍的感应范围内时，按钮整体产生最大 14px 的平滑吸附偏移；
3. 内部文字与图标产生最大 22px 的同向位移，营造双层视差流体感；
4. 鼠标离开感应区后，使用物理弹簧动画回弹复位（stiffness: 180, damping: 14）；
5. 移动端触摸屏（pointer: coarse）环境自动禁用位移计算，保持原生手感。
```

### 5.2 卡片聚光灯光晕 (Spotlight Hover) 注入模版
```markdown
请为这组 [卡片容器选择器] 增加类似 Linear/Aceternity 的鼠标聚光灯高亮微交互：
1. 在卡片外层容器上监听 onMouseMove，计算光标相对于当前卡片的像素坐标 (x, y)；
2. 在卡片内放置一个绝对定位、全覆盖、pointer-events: none 的伪层；
3. 伪层应用 radial-gradient(400px circle at var(--mouse-x) var(--mouse-y), rgba(255,255,255,0.08), transparent 80%)；
4. 鼠标进入卡片时透明度从 0 平滑淡入为 1，离开后淡出，使卡片边缘在鼠标划过时泛出细腻微光。
```

### 5.3 列表平滑重排 (FLIP List Transition) 注入模版
```markdown
当前卡片列表在分类切换时存在瞬间瞬移与闪烁，请基于 FLIP 原理进行平滑重排改造：
1. 使用 Framer Motion 为每个列表项赋予 layout 属性；
2. 筛选发生变化时，保留在屏幕上的卡片使用 spring 弹簧曲线（stiffness: 300, damping: 28）平滑位移至新网格位置；
3. 被剔除的卡片使用 AnimatePresence 进行 scale: 0.9 叠加 opacity: 0 的退出动画；
4. 新进入的卡片错峰（stagger: 0.05s）淡入上浮。
```

---

## 6. 老旧丑陋网页重构与去 AI 油腻感审计模版

```markdown
请你扮演最严苛的 Design Engineering 代码与设计审计师。我们现在有一个充满“AI 模板味”的糟糕网页，请对其进行脱胎换骨式的重构：

【现有毒瘤诊断清单】
1. 检查并移除所有泛滥的 AI 紫色/蓝粉放射模糊光球；
2. 检查并拆除单调死板的三等分对称卡片，将其重构成有主有次、信息密度分明的 Bento Grid；
3. 检查大标题：移除所有千篇一律的居中大标题，重新设计排版层次，加入紧凑负字距（tracking-tight）；
4. 检查文字行宽：正文如果横跨整个屏幕，强行收紧至 65ch 以内；
5. 检查微交互：补充按钮的 active 物理下按反馈（active:scale-[0.98]）、输入框的 focus-visible 光圈、模态窗的原点缩放展开；
6. 检查状态：补齐数据加载时的 Shimmer 骨架屏和空状态引导容器。

请直接输出重构后的清晰结构与完整代码。
```
