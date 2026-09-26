# vibe-frontend-design 🎨⚡

<p align="center">
  <strong>The Anti-Slop Design Engineering Skill for AI Coding Agents.</strong><br>
  <em>把模糊的审美感觉，转化为 AI 与浏览器能 100% 精确执行的确定性工程资产。</em>
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License: MIT"></a>
  <a href="#installation"><img src="https://img.shields.io/badge/Claude%20Code-Compatible-purple.svg" alt="Claude Code"></a>
  <a href="#installation"><img src="https://img.shields.io/badge/Cursor%20%2F%20Codex-Ready-emerald.svg" alt="Cursor Ready"></a>
  <a href="#credits"><img src="https://img.shields.io/badge/Design%20Engineering-Craft-orange.svg" alt="Craft"></a>
</p>

---

## 🌟 为什么需要这个 Skill？(Why vibe-frontend-design?)

在用 AI（Claude Code、Cursor、Windsurf、Codex）写前端时，大多数人都会遭遇以下痛点：
1. **千篇一律的 AI 模板味 (AI Slop)**：默认的紫色/粉色放射发光大球、无脑三等分对称卡片、未调整字距的松垮大标题；
2. **只会说模糊形容词**：向 AI 提需求只会输入“帮我做一个高级、有质感、像苹果那样的界面”，AI 只能靠猜；
3. **动效生硬假滑**：所有元素同节奏淡入、缺少物理阻尼、点击无按压反馈、折叠菜单生硬跳变；
4. **中文字体排版灾难**：中西文挤压、标点掉落行首、在现代深色界面中排版松散。

**`vibe-frontend-design` 是全网首个融合 X 爆款博主 Adrian Punk 全套视觉与动效词典、GitHub 20 万星顶流前端工程生态，以及中西文排版美学的模块化 Agent 技能库。**

---

## 📚 模块化知识库全景 (Modular Architecture)

依据 [Anthropic 官方 Skill 规范](https://github.com/anthropics/skills) 的渐进式披露（Progressive Disclosure）原则，本仓库划分为主执行蓝图与 7 本专项参考专著（总计超 120 KB 纯干货）：

```
vibe-frontend-design/
├── SKILL.md                          # 主蓝图：Design Read、三档旋钮系统、Anti-Slop 十大禁令、12 维走查
└── references/
    ├── visual-dictionary.md          # 视觉词典全书：Bento Grid、Split-screen、5 大现代风格、设计令牌
    ├── motion-dictionary.md          # 动效与物理全书：四层动效法则、多层视差 0.3x/1.0x/1.4x、弹簧回弹
    ├── code-recipes.md               # 12 套生产级源码：磁吸按钮、聚光灯卡片、3D 悬停卡、CSS 手风琴
    ├── prompt-cookbook.md            # 提示词任务书：八字段任务书架构、SaaS 官网、作品集完整 Prompt
    ├── chinese-typography.md         # 中文字体排版指南：1.25 中文字阶、盘古之白、大标题紧凑负字距
    ├── archive-aesthetic.md          # 档案美学体系：Knolling 正交网格、漫反射柔光、标本元件化
    ├── design-engineering-qa.md      # 设计工程排错手册：z-index 层叠矩阵、CLS=0 布局防抖、GPU 加速
    └── github-highstar-ecosystem.md  # 20 万星顶流深度解密：shadcn, Magic UI, Aceternity, cmdk, sonner
```

---

## ⚡ 核心功能与亮点 (Key Features)

### 1. 三档旋钮参数化系统 (The Three Dials)
在让 AI 生成代码前，参数化锁定设计风格，杜绝随机发挥：
- **`DESIGN_VARIANCE` (1 - 10)**：1 = 严谨对称中庸 ➔ 10 = 激进艺术实验不对称
- **`MOTION_INTENSITY` (1 - 10)**：1 = 严谨静态 ➔ 10 = 电影级流体物理与视差
- **`VISUAL_DENSITY` (1 - 10)**：1 = 艺术画廊高留白 ➔ 10 = 高密度控制台仪表盘

### 2. 独门八字段任务书框架 (The 8-Field Spec Prompt)
将“提需求”升华为“下发工程任务书”：
`Role (复合角色) ➔ Goal (单一核心转化) ➔ Audience (受众与设备) ➔ Pages (区块清单) ➔ IA (视觉动线) ➔ Design System (调色板与字阶) ➔ States (全状态闭环) ➔ Acceptance (无横向溢出走查)`。

### 3. 12 套生产级 React + Tailwind + Framer 源码配方
内置经真实浏览器走查的工业级源码：
- 🧲 **双层视差磁吸按钮 (`MagneticButton`)**：文字与外框差速牵引，触屏安全降级；
- 💡 **动态光标聚光灯卡片 (`SpotlightCard`)**：监听鼠标坐标注入径向渐变流光；
- 🃏 **真 3D 透视分层卡片 (`Tilt3DCard`)**：鼠标悬停产生具有 Z 轴深度的立体浮出；
- 🪟 **纯 CSS 零重排手风琴 (`ZeroJsAccordion`)**：`grid-template-rows: 0fr -> 1fr` 丝滑展开；
- ⚡ **Magic UI 边框光束 (`BorderBeamCard`)**：CSS 导轨流光扫过 1px 细线边框；
- ⏱️ **零 CLS 高光波纹骨架屏 (`ShimmerSkeleton`)**：1:1 复刻最终轮廓，杜绝布局抖动。

### 4. 2026 现代中文字体与档案美学
- 中文字阶黄金行高（`1.65 - 1.75`），解决大标题松垮问题（紧凑负字距 `-0.02em`）；
- 中西文自动插入 `0.25em` 盘古之白，严格标点避头尾；
- 融入 Kimi Archive 档案美学：正交平铺（Knolling）、漫反射柔光、微型标本编号印戳。

---

## 🚀 安装与使用指南 (Installation & Usage)

### 方式 1：在 Claude Code 中全局使用（推荐）
直接克隆到用户全局技能目录，即可在所有本地项目中随叫随到：
```bash
# 创建目录并拉取技能库
mkdir -p ~/.claude/skills
git clone https://github.com/<your-username>/vibe-frontend-design.git ~/.claude/skills/vibe-frontend-design
```

### 方式 2：在具体项目中使用
在任意前端项目的根目录下运行：
```bash
mkdir -p .claude/skills
git clone https://github.com/<your-username>/vibe-frontend-design.git .claude/skills/vibe-frontend-design
```

### 方式 3：在 Cursor / Windsurf / Codex 中使用
将本仓库的 `SKILL.md` 与相关参考文档放入 `.cursorrules` 或在 Prompt 中直接引用：
> “请严格按照 `vibe-frontend-design` 规范中的八字段任务书框架，为我设计一个 [SaaS 落地页首屏]。”

---

## 💬 实际使用示范 (Usage Example)

在终端中启动 Claude Code：
```bash
claude
```
直接呼叫 Skill：
```
/vibe-frontend-design
```
或直接在 Prompt 中要求：
> “**调用 vibe-frontend-design 技能**，参考 `prompt-cookbook.md` 中的八字段任务书框架，为我设计一个暗调现代极简风格的 [AI 数据监控看板]。”

**AI 将自动执行**：
1. 输出一行 **`Design Read`** 与 **`Three Dials`** 设定风格基调；
2. 自动封杀所有 AI 垃圾模板套话；
3. 从 `chinese-typography.md` 提取紧凑字距与排版规范；
4. 直接复用 `code-recipes.md` 中的生产级磁吸、聚光灯与 Bento Grid 源码交付！

---

## 🤝 致谢与灵感来源 (Credits & Inspirations)

本项目的诞生离不开以下顶尖创作者与开源先驱的启发：

* **特别致谢：[Adrian Punk (@AdrianPunk115)](https://x.com/AdrianPunk115)**  
  本技能的视觉与动效词典体系深受其 X 爆款长文《Vibe Coding 视觉词典》、《Vibe Coding 网页动效词典》、《2026 中文字体 AI 提示词指南》与《Kimi Archive 档案美学体系》的深刻启发。
* **[Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill)**：感谢其首创的 Anti-Slop 理念、Design Read 与三档旋钮系统。
* **[shadcn/ui](https://github.com/shadcn-ui/ui)** & **[Radix UI](https://github.com/radix-ui/primitives)**：无样式可访问性基石。
* **[magicuidesign/magicui](https://github.com/magicuidesign/magicui)** & **[aceternity/ui](https://github.com/aceternity/ui)**：现代微动效与震撼视觉呈现。
* **[DavidHDev/react-bits](https://github.com/DavidHDev/react-bits)**：丰富的创意动画与文本解密动效。
* **[Emil Kowalski](https://emilkowal.ski/)** ([animations.dev](https://animations.dev/), [sonner](https://github.com/emilkowalski/sonner), [vaul](https://github.com/emilkowalski/vaul)) 与 **[Paco Coursey](https://paco.me/)** ([cmdk](https://github.com/pacocoursey/cmdk))：手艺级交互设计工程学的布道者。
* **[ibelick](https://github.com/ibelick)**：质感底纹与噪点美学启发。

---

## 📄 开源许可证 (License)

本项目采用 [MIT License](LICENSE) 开源。欢迎 Star、Fork、提 PR 或在社区中自由分享！
