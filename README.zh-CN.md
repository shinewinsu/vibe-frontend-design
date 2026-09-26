<p align="center">
  <img src="assets/hero-banner.svg" alt="vibe-frontend-design" width="100%" />
</p>

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-8A2BE2.svg?style=flat-square)](https://github.com/anthropics/claude-code)
[![Cursor](https://img.shields.io/badge/Cursor%20%2F%20Windsurf-Ready-10b981.svg?style=flat-square)](https://cursor.com)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS%20v3%20%2F%20v4-38bdf8.svg?style=flat-square)](https://tailwindcss.com)
[![Framer Motion](https://img.shields.io/badge/Framer%20Motion-Physics-ff0055.svg?style=flat-square)](https://motion.dev)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/shinewinsu/vibe-frontend-design/pulls)

<br />

[ English ](README.md) &nbsp;|&nbsp; [ 简体中文 ](README.zh-CN.md)

</div>

---

## 拒绝前端代码里的 AI 油腻味 (Anti-Slop Manifesto)

绝大多数大语言模型（Claude、GPT、DeepSeek）在没有任何设计工程约束时，写出来的界面几乎共享同一副面孔：
- 漆黑底板上漂浮着刺眼的紫色/粉色放射状模糊光斑（Mesh Gradient Blobs）；
- 无脑对称的三等分卡片排布，毫无视觉重心与信息层级；
- 标题字距松散散漫，中西文紧贴挤压，标点掉落行首；
- 按钮点击没有任何物理按压反馈，所有元素用同一个机械速度同时淡入；
- 展开菜单或切换标签时布局生硬跳变，数据加载引发剧烈抖动。

**这不是“高级”，这是最低公约数的偷懒。**

`vibe-frontend-design` 是一套专为现代 AI 编程智能体（Claude Code、Cursor、Windsurf、Codex）打造的**高品味设计工程学（Design Engineering）技能库**。它将原本抽象的审美感觉，拆解为浏览器与大模型能够 100% 精确执行的确定性工程资产：**模块化字阶、表面四层体系、双层视差物理弹簧、非对称 Bento Grid、中西文排版避头尾法则与 12 套生产级源码**。

---

## 视觉与工程对比 (The Contrast)

<p align="center">
  <img src="assets/before-after.svg" alt="Before vs After Visual Comparison" width="100%" />
</p>

| 维度 | 普通 AI 默认生成 (Generic AI Slop) | vibe-frontend-design 驱动 (The Craft) |
|---|---|---|
| **页面布局** | 单调死板的三等分对称卡片（3-Column Equal Cards） | **非对称 Bento Grid（便当盒网格）**，2x2 主角拓扑卡 + 错落指标卡 |
| **色彩光影** | 纯黑底配高饱和紫色大光斑，塑料感严重 | **表面四层体系**（Level 0 Canvas -> Level 3 Overlay），1px 细线发光微边框 |
| **动效物理** | 全屏元素无脑同速淡入，机械僵硬 | **50ms 交错级联上浮（Stagger）**，物理弹簧阻尼（`stiffness: 180, damping: 14`） |
| **交互手感** | 按钮悬停无张力，点击无下按反馈 | **双层视差磁吸按钮（Magnetic Button）**，点击物理缩放 `active:scale-[0.98]` |
| **中文字体** | 默认行高拥挤，大标题松垮，标点掉行首 | **1.25 中文字阶黄金律**，大标题紧凑负字距（`-0.02em`），中西文盘古之白 |
| **加载性能** | 全屏突兀白屏，数据返回瞬间布局剧烈抖动 | **1:1 轮廓高光波纹骨架屏（Shimmer）**，纯 CSS 零重排手风琴，**CLS = 0** |

---

## 真实交互效果演练场 (Live Interactive Demo)

本项目自带**无需任何构建环境、开箱即用的真实交互演示页面**（`demo/index.html`）：
- **运行方式**：直接双击 `demo/index.html`，或在终端执行 `open demo/index.html`。
- **可把玩的真实物理微交互**：
  - **双层磁吸按钮**：光标靠近产生引力拉扯，文字额外视差位移，移出弹簧自然回弹；
  - **动态聚光灯卡片**：径向渐变微光紧跟鼠标像素坐标流动，激活 1px 细发光边框；
  - **真 3D 透视分层卡片**：随鼠标角度产生立体空间倾斜，内部文字按钮 Z 轴浮出；
  - **赛博字符解密动画**：鼠标悬停触发黑客终端级字符翻滚解码；
  - **纯 CSS 零重排手风琴**：点击瞬间 60fps 丝滑展开，杜绝 JS 测量高度导致的掉帧；
  - **高光波纹骨架屏**：1:1 复刻最终轮廓，实现累积布局偏移 CLS = 0。

<p align="center">
  <img src="assets/bento-showcase.svg" alt="Bento Grid Animated Showcase" width="100%" />
</p>

---

## 核心系统架构 (Core Systems)

### 1. 三档旋钮参数化系统 (The Three Dials)
在让 AI 生成代码前，通过参数锁定设计基调，彻底封死模型的平庸退路：
- **`DESIGN_VARIANCE` (1 - 10)**：1 = 严谨对称中庸 -> 10 = 激进艺术实验不对称
- **`MOTION_INTENSITY` (1 - 10)**：1 = 严谨静态 -> 10 = 电影级流体物理与多层视差
- **`VISUAL_DENSITY` (1 - 10)**：1 = 艺术画廊高留白 -> 10 = 专业控制台仪表盘

### 2. 八字段任务书架构 (The 8-Field Spec Prompt)
将模糊聊天升级为标准工程任务书：
`Role (复合角色) -> Goal (单一核心转化) -> Audience (受众与设备) -> Pages (区块清单) -> IA (视觉动线) -> Design System (调色板与字阶) -> States (全状态闭环) -> Acceptance (零横向溢出走查)`。

### 3. 12 套生产级源码配方库 (Production Code Recipes)
内置经过真实浏览器走查的工业级源码（存放在 `references/code-recipes.md`）：
- 磁吸按钮 (`MagneticButton`)：双层视差 + 弹簧阻尼 + 触屏降级；
- 聚光灯卡片 (`SpotlightCard`)：局部动态径向高光；
- 真 3D 透视卡 (`Tilt3DCard`)：CSS perspective + transformZ 分层；
- 零重排手风琴 (`ZeroJsAccordion`)：现代 CSS Grid 60fps 展开；
- 流光边框卡片 (`BorderBeamCard`)：Magic UI 算法沿边界扫光；
- 赛博解密文字 (`DecryptedText`)：高频随机字符翻滚解码；
- 胶片噪点底层 (`MaskedNoiseBackground`)：3.5% 免下载 SVG 分形微粒。

<p align="center">
  <img src="assets/magnetic-spring.svg" alt="Magnetic Button Physics Simulation" width="100%" />
</p>

### 4. 2026 现代中文字体与档案美学
- 中文字阶黄金行高（`1.65 - 1.75`），解决大标题松垮问题（负字距 `-0.02em`）；
- 中西文自动插入 `0.25em` 盘古之白，严格标点避头尾；
- 融入 Kimi Archive 档案美学：正交平铺（Knolling）、漫反射柔光箱阴影、微型标本编号印戳。

---

## 模块化参考手册全景 (超 120 KB 纯干货)

遵循 Anthropic 官方 Skill 规范的**渐进式披露（Progressive Disclosure）**原则，分为主蓝图与 7 本专项参考专著：

```
vibe-frontend-design/
├── SKILL.md                          # 主蓝图：Design Read、三档旋钮系统、Anti-Slop 十大禁令、12 维自检清单
├── LICENSE                           # MIT 开源协议
├── demo/
│   └── index.html                    # 真实交互演练场（双击即玩）
└── references/
    ├── visual-dictionary.md          # 视觉全书：Bento Grid、Split-screen、5 大现代风格、设计令牌
    ├── motion-dictionary.md          # 动效全书：四层动效法则、多层视差 0.3x/1.0x/1.4x、弹簧回弹
    ├── code-recipes.md               # 12 套生产级源码：磁吸按钮、聚光灯卡片、3D 悬停卡、CSS 手风琴
    ├── prompt-cookbook.md            # 提示词任务书：八字段任务书架构、SaaS 官网、作品集完整 Prompt
    ├── chinese-typography.md         # 中文字体排版指南：1.25 中文字阶、盘古之白、大标题紧凑负字距
    ├── archive-aesthetic.md          # 档案美学体系：Knolling 正交网格、漫反射柔光、标本元件化
    ├── design-engineering-qa.md      # 设计工程排错手册：z-index 层叠矩阵、CLS=0 布局防抖、GPU 加速
    └── github-highstar-ecosystem.md  # 20 万星顶流深度解密：shadcn, Magic UI, Aceternity, cmdk, sonner
```

---

## 安装与使用指南 (Installation & Usage)

### 方式 1：在 Claude Code 中全局使用（推荐）
直接克隆到用户全局技能目录，即可在本地所有项目中随叫随到：
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/shinewinsu/vibe-frontend-design.git ~/.claude/skills/vibe-frontend-design
```

### 方式 2：在具体前端项目中生效
在任意前端项目的根目录下运行：
```bash
mkdir -p .claude/skills
git clone https://github.com/shinewinsu/vibe-frontend-design.git .claude/skills/vibe-frontend-design
```

### 方式 3：在 Cursor / Windsurf / Codex 中使用
将本仓库的 `SKILL.md` 放入 `.cursorrules` 或在 Prompt 中直接引用：
> “请严格按照 `vibe-frontend-design` 规范中的八字段任务书框架，为我设计一个 [SaaS 落地页首屏]。”

---

## 终端调用实战 (Terminal Usage)

在 Claude Code 终端中直接输入：
```bash
/vibe-frontend-design
```
或在自然语言 Prompt 中下达需求：
> “调用 vibe-frontend-design 技能，参考 `prompt-cookbook.md` 中的八字段任务书框架，为我设计一个暗调现代极简风格的 [AI 数据监控看板]。”

**AI 将全自动执行**：
1. 输出一行 **`Design Read`** 与 **`Three Dials`** 锁定风格基调；
2. 自动屏蔽所有 AI 油腻模板与紫色渐变大光斑；
3. 从 `chinese-typography.md` 提取紧凑负字距与盘古排版间距；
4. 直接调用 `code-recipes.md` 中的生产级磁吸、聚光灯与 Bento Grid 源码高质量交付！

---

## 致谢与灵感来源 (Credits & Inspirations)

本项目的诞生深受以下顶尖创作者与开源先锋的深刻启发：

- **特别致谢：[Adrian Punk (@AdrianPunk115)](https://x.com/AdrianPunk115)**  
  本技能的核心词典与任务书体系深受其 X 爆款长文《Vibe Coding 视觉词典》、《Vibe Coding 网页动效词典》、《2026 中文字体 AI 提示词指南》与《Kimi Archive 档案美学体系》的深刻启发。
- **[Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill)**：感谢其首创的 Anti-Slop 理念、Design Read 与三档旋钮系统。
- **[shadcn/ui](https://github.com/shadcn-ui/ui)** & **[Radix UI](https://github.com/radix-ui/primitives)**：无样式可访问性基石。
- **[magicuidesign/magicui](https://github.com/magicuidesign/magicui)** & **[aceternity/ui](https://github.com/aceternity/ui)**：现代微动效与震撼视觉呈现。
- **[DavidHDev/react-bits](https://github.com/DavidHDev/react-bits)**：丰富的创意动画与文本解密动效。
- **[Emil Kowalski](https://emilkowal.ski/)** ([animations.dev](https://animations.dev/), [sonner](https://github.com/emilkowalski/sonner), [vaul](https://github.com/emilkowalski/vaul)) 与 **[Paco Coursey](https://paco.me/)** ([cmdk](https://github.com/pacocoursey/cmdk))：手艺级交互设计工程学的布道者。
- **[ibelick](https://github.com/ibelick)**：质感底纹与噪点美学启发。

---

## 开源许可证 (License)

本项目采用 [MIT License](LICENSE) 开源。欢迎 Star、Fork、提 PR 或在社区中自由分享！
