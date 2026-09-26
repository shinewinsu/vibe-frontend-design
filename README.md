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

## Stop Accepting AI Slop in Your Frontends (Anti-Slop Manifesto)

When left unguided, modern LLMs (Claude, GPT, DeepSeek) default to the same tired visual clichés:
- Predictable pitch-black canvases dominated by oversaturated purple and pink glowing mesh blobs.
- Symmetrical, equal-sized 3-column feature cards with zero information hierarchy.
- Loose, unadjusted headline tracking and text wrapping that breaks awkwardly.
- Static buttons that lack physical press feedback, while every element fades in simultaneously at the exact same mechanical speed.
- Collapsing accordions and tabs that trigger severe layout shifts (CLS) and dropped frames.

**This is not premium design. It is the lowest common denominator of unopinionated code generation.**

`vibe-frontend-design` is an opinionated **Design Engineering Skill** built for modern AI coding agents (Claude Code, Cursor, Windsurf, Codex). It converts abstract aesthetic taste into deterministic, mathematically grounded frontend assets: **modular typography scales, 4-tier surface hierarchies, double-layer spring physics, asymmetric Bento Grids, zero-CLS layout primitives, and 12 production-grade code recipes.**

---

## The Contrast: Generic AI Slop vs. Design Engineering Craft

<p align="center">
  <img src="assets/before-after.svg" alt="Before vs After Visual Comparison" width="100%" />
</p>

| Dimension | Generic AI Generation (The Slop) | vibe-frontend-design (The Craft) |
|---|---|---|
| **Layout** | Symmetrical 3-column equal cards with no visual focal point | **Asymmetric Bento Grid**, with a 2x2 Hero Anchor Tile and offset metric cards |
| **Surfaces & Color** | Harsh pitch-black with oversaturated glowing purple blobs | **4-Level Surface Hierarchy** (Level 0 Canvas -> Level 3 Overlay), 1px hairline border, cursor spotlight |
| **Motion Physics** | All cards fade in simultaneously with linear, mechanical easing | **50ms Stagger Cascade**, physical spring damping (`stiffness: 180, damping: 14`) |
| **Tactile Feedback** | Static buttons with zero press feedback | **Double-Layer Magnetic Button**, tactile press feedback `active:scale-[0.98]` |
| **Typography** | Default line-height, loose tracking, awkward line breaks | **Modular Scale 1.25**, tight headline tracking (`-0.02em`), 65ch measure limit |
| **Perceived Perf** | Blank loading states, jarring content jumps | **1:1 Shimmer Skeleton Screen**, pure CSS zero-reflow accordion, **CLS = 0** |

---

## Live Interactive Demo (Zero Dependencies)

This repository includes a standalone interactive showcase page (`demo/index.html`):
- **How to run**: Simply double-click `demo/index.html` or execute `open demo/index.html` in your terminal.
- **Interactive features ready to test**:
  - **Double-Layer Magnetic Button**: Cursor attraction with differential parallax between button body and inner text, settling via physical spring oscillation.
  - **Dynamic Cursor Spotlight**: Real-time radial gradient tracking mouse coordinates across 1px borders.
  - **3D Perspective Tilt Card**: True spatial tilt along the X/Y axes with Z-axis elevation (`translateZ`).
  - **Decrypted / Scramble Text**: Cyberpunk-style glyph rolling and progressive left-to-right character resolving.
  - **Pure CSS Zero-Layout-Thrashing Accordion**: Smooth 60fps grid height expansion without JavaScript `scrollHeight` reflows.
  - **Shimmer Skeleton Screen**: 1:1 blueprint outline with zero Cumulative Layout Shift (CLS = 0).

<p align="center">
  <img src="assets/bento-showcase.svg" alt="Bento Grid Animated Showcase" width="100%" />
</p>

---

## Core Systems & Architecture

### 1. The Three Dials Configuration
Before generating code, the agent infers and locks three baseline parameters:
- **`DESIGN_VARIANCE` (1 - 10)**: 1 = Conservative Symmetry -> 10 = Asymmetric Experimental Art
- **`MOTION_INTENSITY` (1 - 10)**: 1 = Clean Static -> 10 = Cinematic Spring Physics & Differential Parallax
- **`VISUAL_DENSITY` (1 - 10)**: 1 = Gallery Negative Space -> 10 = Dense Mission-Critical Dashboard

### 2. The 8-Field Spec Prompt Architecture
Upgrades conversational prompting into a structured engineering specification:
`Role (Composite Specialist) -> Goal (Single Primary Conversion) -> Audience (Context & Device) -> Pages (Block Inventory) -> IA (F-Pattern Flow) -> Design System (Tokens & Modular Scale) -> States (Full State Machine) -> Acceptance (Zero-Overflow Criteria)`

### 3. Production Code Recipes (`references/code-recipes.md`)
Includes 12 battle-tested component implementations built with React, Tailwind CSS, and Framer Motion:
- Double-layer Magnetic Button with touchscreen fallback;
- Dynamic Spotlight Card with relative coordinate injection;
- True 3D Perspective Tilt Card;
- Pure CSS Grid Auto-height Accordion;
- Magic UI Border Beam Card;
- Scramble Decrypted Text;
- Masked Film Grain Noise Background.

<p align="center">
  <img src="assets/magnetic-spring.svg" alt="Magnetic Button Physics Simulation" width="100%" />
</p>

### 4. Global & CJK Typography Standards
- Modular scale 1.25 with tight headline tracking (`-0.02em` to `-0.025em`) to prevent visual scatter;
- Pangu spacing (`0.25em`) between East Asian characters and Latin/numeric glyphs;
- Strict line-breaking rules (`text-wrap: pretty; line-break: strict`) to prevent orphan characters;
- Integrated Kimi Archive aesthetic: orthogonal knolling grids, diffuse softbox lighting, and technical specimen stamp details.

---

## Modular Knowledge Base Index (Over 120 KB)

Adheres to Anthropic's **Progressive Disclosure** specification, separating the master blueprint from 7 specialized reference manuals:

```
vibe-frontend-design/
├── SKILL.md                          # Master Blueprint: Design Read, Three Dials, Anti-Slop Prohibitions, 12-Point QA Matrix
├── LICENSE                           # MIT License
├── README.md                         # English Documentation
├── README.zh-CN.md                   # 简体中文文档
├── demo/
│   └── index.html                    # Live Interactive Showcase (Zero Dependencies)
└── references/
    ├── visual-dictionary.md          # Visual Encyclopedia: Bento Grid, Split-Screen, 5 Aesthetic Styles, Surface Tokens
    ├── motion-dictionary.md          # Motion Encyclopedia: 4-Layer Motion Framework, Parallax 0.3x/1.0x/1.4x, Springs
    ├── code-recipes.md               # 12 Production React + Tailwind Code Implementations
    ├── prompt-cookbook.md            # The 8-Field Mini-Spec Prompt Architecture & Templates
    ├── chinese-typography.md         # CJK Typography Standards: Modular Scales, Pangu Spacing, Negative Tracking
    ├── archive-aesthetic.md          # Archive Aesthetic & Knolling System: Orthogonal Grids, Diffuse Softbox Lighting
    ├── design-engineering-qa.md      # Design Engineering QA: Stacking Context Matrix, Zero-CLS Architecture
    └── github-highstar-ecosystem.md  # 200k+ Stars Ecosystem: Architecture of shadcn/ui, Magic UI, Aceternity, cmdk
```

---

## Installation & Quickstart

### Method 1: Global Installation in Claude Code (Recommended)
Clone into your global user skills directory to make it immediately available across all local projects:
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/shinewinsu/vibe-frontend-design.git ~/.claude/skills/vibe-frontend-design
```

### Method 2: Per-Project Installation
Install directly inside a specific frontend repository:
```bash
mkdir -p .claude/skills
git clone https://github.com/shinewinsu/vibe-frontend-design.git .claude/skills/vibe-frontend-design
```

### Method 3: Cursor / Windsurf / Codex Integration
Place `SKILL.md` inside your `.cursorrules` or reference it explicitly in your prompt:
> "Strictly follow the `vibe-frontend-design` specification and 8-field spec architecture to design a modern B2B SaaS landing page hero."

---

## Terminal Usage

In Claude Code, invoke the skill directly:
```bash
/vibe-frontend-design
```
Or trigger it through natural language:
> "Invoke the vibe-frontend-design skill. Use the 8-field spec architecture from `prompt-cookbook.md` to design a Linear-style dark dashboard for distributed AI monitoring."

**The Agent will automatically**:
1. Output a one-line **`Design Read`** and lock **`The Three Dials`**;
2. Enforce Anti-Slop constraints, eliminating default purple blobs and generic card grids;
3. Apply modular typography with tight tracking and 65ch measure limits;
4. Supply battle-tested, production-ready code directly from `code-recipes.md`.

---

## Credits & Prior Art

This project is deeply inspired by pioneering design engineers and open-source creators:

- **Special Recognition: [Adrian Punk (@AdrianPunk115)](https://x.com/AdrianPunk115)**  
  The visual and motion dictionaries, 8-field spec prompt architecture, and archive aesthetic standards are deeply grounded in Adrian Punk's viral series on X.
- **[Leonxlnx/taste-skill](https://github.com/Leonxlnx/taste-skill)**: For pioneering the Anti-Slop philosophy, Design Read, and The Three Dials system.
- **[shadcn/ui](https://github.com/shadcn-ui/ui)** & **[Radix UI](https://github.com/radix-ui/primitives)**: The standard for accessible, unstyled UI primitives.
- **[magicuidesign/magicui](https://github.com/magicuidesign/magicui)** & **[aceternity/ui](https://github.com/aceternity/ui)**: For modern animated marketing components and 3D visual spectacle.
- **[DavidHDev/react-bits](https://github.com/DavidHDev/react-bits)**: Creative interactive animation patterns and decrypted text effects.
- **[Emil Kowalski](https://emilkowal.ski/)** ([animations.dev](https://animations.dev/), [sonner](https://github.com/emilkowalski/sonner), [vaul](https://github.com/emilkowalski/vaul)) & **[Paco Coursey](https://paco.me/)** ([cmdk](https://github.com/pacocoursey/cmdk)): For defining the craft of interaction design and tactile desktop-grade web software.
- **[ibelick](https://github.com/ibelick)**: For background snippet craftsmanship and noise overlay textures.

---

## License

This project is licensed under the [MIT License](LICENSE). Feel free to star, fork, submit PRs, and share with the community!
