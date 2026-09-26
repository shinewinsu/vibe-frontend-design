<div align="center">

# vibe-frontend-design

<p>
  <strong>面向 AI 编程智能体的高品味设计工程学（Design Engineering）技能库</strong><br />
  把模糊的审美感觉，转化为 AI 与浏览器能 100% 精确执行的确定性工程资产。
</p>

<p>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-090a0f.svg?style=flat-square" alt="License: MIT" /></a>
  <a href="#安装与使用指南-installation--usage"><img src="https://img.shields.io/badge/Claude%20Code-Compatible-090a0f.svg?style=flat-square" alt="Claude Code" /></a>
  <a href="#安装与使用指南-installation--usage"><img src="https://img.shields.io/badge/Cursor%20%2F%20Windsurf-Ready-090a0f.svg?style=flat-square" alt="Cursor Ready" /></a>
  <a href="#致谢与灵感来源-credits--prior-art"><img src="https://img.shields.io/badge/Craft-Design%20Engineering-090a0f.svg?style=flat-square" alt="Craft" /></a>
</p>

<p>
  <a href="README.md"><strong>English Documentation</strong></a> &middot;
  <a href="README.zh-CN.md"><strong>简体中文文档</strong></a> &middot;
  <a href="#真实交互效果演练场-live-interactive-demo"><strong>真实交互演示</strong></a> &middot;
  <a href="#视觉与工程对比-the-contrast"><strong>效果对比</strong></a> &middot;
  <a href="#安装与使用指南-installation--usage"><strong>快速安装</strong></a>
</p>

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

`vibe-frontend-design` 是一套专为现代 AI 编程智能体（Claude Code、Cursor、Windsurf、Codex）打造的**高品味设计工程学（Design Engineering）技能库**。它将原本抽象的审美感觉，拆解为浏览器与大模型能够 100% 精确执行的确定性工程资产：**模块化字阶（1.25 比率）、表面四层体系、双层视差物理弹簧、非对称 Bento Grid、中西文排版避头尾法则与 12 套生产级源码**。

---

## 视觉与工程对比 (The Contrast)

```
[普通 AI 默认生成的无脑三等分对称卡片 (The Slop)]
+---------------+---------------+---------------+
|    Card 1     |    Card 2     |    Card 3     |
| (全量等宽)    | (全量等宽)    | (全量等宽)    |
+---------------+---------------+---------------+
毫无视觉焦点。毫无信息层级。机械单调。

[本技能驱动的非对称 Bento Grid 黄金网格 (The Craft)]
+-------------------------------+---------------+
|                               | 指标副卡 01   |
|       HERO ANCHOR TILE        +---------------+
|       (2x2 主角大卡)          | 指标副卡 02   |
|     核心可视化拓扑画布        +---------------+
|                               | 横向功能卡片  |
+-------------------------------+---------------+
视觉焦点明确。呼吸节奏分明。浏览动线清晰。
```

### 技术维度对比矩阵

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

本项目自带**无需任何构建环境、开箱即用的真实交互演示页面**（[`demo/index.html`](demo/index.html)）：
- **运行方式**：直接双击 `demo/index.html`，或在终端执行：
  ```bash
  # macOS
  open demo/index.html

  # Linux
  xdg-open demo/index.html

  # Windows
  start demo/index.html
  ```
- **可把玩的真实物理微交互**：
  - **双层磁吸按钮**：1.5 倍感应半径，外框 14px 牵引位移，文字 20px 额外视差位移，移出弹簧自然回弹；
  - **动态聚光灯卡片**：径向渐变微光紧跟鼠标像素坐标流动，激活 1px 细发光边框；
  - **真 3D 透视分层卡片**：随鼠标角度产生立体空间倾斜，内部文字按钮 Z 轴悬浮浮出（`translateZ`）；
  - **赛博字符解密动画**：鼠标悬停触发黑客终端级字符翻滚解码；
  - **纯 CSS 零重排手风琴**：点击瞬间 60fps 丝滑展开，解决传统测量 scrollHeight 引起的重排掉帧；
  - **高光波纹骨架屏**：1:1 复刻最终轮廓，实现累积布局偏移 CLS = 0。

---

## 核心系统架构 (Core Systems)

### 1. 三档旋钮参数化系统 (The Three Dials)
在让 AI 生成代码前，通过参数锁定设计基调，彻底封死模型的平庸退路：
```markdown
DESIGN_VARIANCE:  [1 - 10]  # 1 = 严谨对称中庸 -> 10 = 激进艺术实验不对称
MOTION_INTENSITY: [1 - 10]  # 1 = 严谨静态     -> 10 = 电影级流体物理与多层视差
VISUAL_DENSITY:   [1 - 10]  # 1 = 艺术画廊高留白 -> 10 = 专业控制台仪表盘
```

### 2. 八字段任务书架构 (The 8-Field Spec Prompt)
将模糊聊天升级为标准工程任务书：
`Role (复合角色) -> Goal (单一核心转化) -> Audience (受众与设备) -> Pages (区块清单) -> IA (视觉动线) -> Design System (调色板与字阶) -> States (全状态闭环) -> Acceptance (零横向溢出走查)`。

---

## 生产级源码配方精选

所有 12 套生产级源码存放在 [`references/code-recipes.md`](references/code-recipes.md)，开箱即用：

### 配方 1：双层视差磁吸按钮 (React + Framer Motion)
```tsx
import React, { useRef, useState } from "react";
import { motion } from "framer-motion";

export function MagneticButton({ children, className = "" }: { children: React.ReactNode; className?: string }) {
  const buttonRef = useRef<HTMLButtonElement>(null);
  const [pos, setPos] = useState({ x: 0, y: 0 });

  const handleMouseMove = (e: React.MouseEvent<HTMLButtonElement>) => {
    if (window.matchMedia("(pointer: coarse)").matches) return; // 触屏安全降级
    if (!buttonRef.current) return;
    const { clientX, clientY } = e;
    const { left, top, width, height } = buttonRef.current.getBoundingClientRect();
    // 0.35 弹簧吸附系数
    setPos({ x: (clientX - (left + width / 2)) * 0.35, y: (clientY - (top + height / 2)) * 0.35 });
  };

  return (
    <motion.button
      ref={buttonRef}
      onMouseMove={handleMouseMove}
      onMouseLeave={() => setPos({ x: 0, y: 0 })}
      animate={{ x: pos.x, y: pos.y }}
      transition={{ type: "spring", stiffness: 180, damping: 14, mass: 0.1 }}
      className={`relative inline-flex items-center justify-center rounded-xl px-6 py-3 select-none active:scale-[0.98] ${className}`}
    >
      <motion.span
        animate={{ x: pos.x * 0.5, y: pos.y * 0.5 }} // 内部文字额外视差位移
        transition={{ type: "spring", stiffness: 220, damping: 16 }}
        className="inline-flex items-center gap-2 pointer-events-none"
      >
        {children}
      </motion.span>
    </motion.button>
  );
}
```

### 配方 2：纯 CSS 零重排高度自适应手风琴 (Zero-JS Grid Accordion)
```css
/* 彻底告别 JS 测量 scrollHeight 引起的重排掉帧 */
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

### 配方 3：动态光标聚光灯卡片 (Dynamic Spotlight Card)
```tsx
import React, { useRef } from "react";

export function SpotlightCard({ children, className = "" }: { children: React.ReactNode; className?: string }) {
  const cardRef = useRef<HTMLDivElement>(null);

  const handleMouseMove = (e: React.MouseEvent<HTMLDivElement>) => {
    if (!cardRef.current) return;
    const rect = cardRef.current.getBoundingClientRect();
    cardRef.current.style.setProperty("--mouse-x", `${e.clientX - rect.left}px`);
    cardRef.current.style.setProperty("--mouse-y", `${e.clientY - rect.top}px`);
  };

  return (
    <div
      ref={cardRef}
      onMouseMove={handleMouseMove}
      className={`group relative rounded-2xl bg-zinc-900/60 p-6 border border-white/10 overflow-hidden ${className}`}
    >
      <div
        className="pointer-events-none absolute -inset-px rounded-2xl opacity-0 transition-opacity duration-300 group-hover:opacity-100"
        style={{
          background: "radial-gradient(450px circle at var(--mouse-x, 0) var(--mouse-y, 0), rgba(255, 255, 255, 0.08), transparent 80%)",
        }}
      />
      <div className="relative z-10">{children}</div>
    </div>
  );
}
```

---

## 模块化参考手册全景 (超 120 KB 纯干货)

遵循 Anthropic 官方 Skill 规范的**渐进式披露（Progressive Disclosure）**原则，分为主蓝图与 7 本专项参考专著：

| 专著文件 | 定位与范畴 | 涵盖核心知识点 |
|---|---|---|
| [`SKILL.md`](SKILL.md) | 主执行蓝图 | Design Read 强制先行、三档旋钮系统、Anti-Slop 十大禁令、12 维质量检查表 |
| [`references/visual-dictionary.md`](references/visual-dictionary.md) | 视觉词典全书 | Bento Grid 便当盒、Split-screen 分屏、5 大现代风格、设计令牌、表面层级 |
| [`references/motion-dictionary.md`](references/motion-dictionary.md) | 动效与物理全书 | 动效四层拆解法则、多层视差 0.3x/1.0x/1.4x 差速、弹簧刚度阻尼公式、FLIP 重排 |
| [`references/code-recipes.md`](references/code-recipes.md) | 工业级代码配方 | 12 套生产级 React + Tailwind + Framer 源码（磁吸、聚光灯、3D 卡片、CSS 手风琴） |
| [`references/prompt-cookbook.md`](references/prompt-cookbook.md) | 提示词任务书库 | 八字段任务书架构、SaaS 官网、作品集、控制台完整 Prompt 模板 |
| [`references/chinese-typography.md`](references/chinese-typography.md) | 中文字体排版指南 | 1.25 中文字阶黄金律、中西文盘古之白（0.25em）、大标题紧凑负字距、标点避头尾 |
| [`references/archive-aesthetic.md`](references/archive-aesthetic.md) | 档案美学体系 | Kimi Archive 正交平铺（Knolling）、漫反射柔光箱阴影、微型标本编号印戳 |
| [`references/design-engineering-qa.md`](references/design-engineering-qa.md) | 设计工程排错手册 | CSS z-index 层叠上下文排查矩阵、CLS=0 布局防抖、GPU 硬件加速走查 |
| [`references/github-highstar-ecosystem.md`](references/github-highstar-ecosystem.md) | 20 万星顶流生态 | shadcn/ui、Magic UI、Aceternity、cmdk、sonner 底层架构全解密 |

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

## 致谢与灵感来源 (Credits & Prior Art)

本项目的诞生深受以下顶尖创作者与开源先锋的深刻启发：

- **特别致谢：[Adrian Punk (@AdrianPunk115)](https://x.com/AdrianPunk115)**：本技能的核心词典与任务书体系深受其 X 爆款长文《Vibe Coding 视觉词典》、《Vibe Coding 网页动效词典》、《2026 中文字体 AI 提示词指南》与《Kimi Archive 档案美学体系》的深刻启发。
- **[Leon Lin / taste-skill](https://github.com/Leonxlnx/taste-skill)**：感谢其首创的 Anti-Slop 理念、Design Read 与三档旋钮系统。
- **[shadcn/ui](https://github.com/shadcn-ui/ui)** & **[Radix UI](https://github.com/radix-ui/primitives)**：无样式可访问性基石。
- **[Magic UI](https://github.com/magicuidesign/magicui)** & **[Aceternity UI](https://github.com/aceternity/ui)**：现代微动效与震撼视觉呈现。
- **[DavidHDev / react-bits](https://github.com/DavidHDev/react-bits)**：创意动画与字符解密动效。
- **[Emil Kowalski](https://emilkowal.ski/)** 与 **[Paco Coursey](https://paco.me/)**：定义了手艺级交互设计工程学、cmdk、vaul 与 sonner。
- **[ibelick](https://github.com/ibelick)**：质感底纹与噪点美学启发。

---

## 开源许可证 (License)

本项目采用 [MIT License](LICENSE) 开源。
