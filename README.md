<div align="center">

# vibe-frontend-design

<p>
  <strong>The Anti-Slop Design Engineering Skill for AI Coding Agents</strong><br />
  Turn vague aesthetic intuition into deterministic, production-grade frontend architecture.
</p>

<p>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-090a0f.svg?style=flat-square" alt="License: MIT" /></a>
  <a href="#installation"><img src="https://img.shields.io/badge/Claude%20Code-Compatible-090a0f.svg?style=flat-square" alt="Claude Code" /></a>
  <a href="#installation"><img src="https://img.shields.io/badge/Cursor%20%2F%20Windsurf-Ready-090a0f.svg?style=flat-square" alt="Cursor Ready" /></a>
  <a href="#credits"><img src="https://img.shields.io/badge/Craft-Design%20Engineering-090a0f.svg?style=flat-square" alt="Craft" /></a>
</p>

<p>
  <a href="README.md"><strong>English Documentation</strong></a> &middot;
  <a href="README.zh-CN.md"><strong>简体中文文档</strong></a> &middot;
  <a href="#live-interactive-demo"><strong>Live Demo</strong></a> &middot;
  <a href="#the-contrast-the-slop-vs-the-craft"><strong>The Contrast</strong></a> &middot;
  <a href="#installation"><strong>Installation</strong></a>
</p>

</div>

---

## The Anti-Slop Manifesto

When asked to build a modern, high-end web interface without explicit constraints, major LLMs (Claude, GPT-4o, DeepSeek) consistently default to the same uninspired visual clichés:

1. **The Purple Mesh Glow**: Pitch-black canvas (`#000000`) drowned in centered, oversaturated purple and pink radial blur blobs (`#a855f7`).
2. **The 3-Card Symmetrical Grid**: Three identical, equal-width cards sitting abreast, displaying zero information hierarchy or visual focal point.
3. **Typography Scatter**: Loose default tracking on large display headings, unconstrained paragraph measures (120ch+), and awkward word wraps.
4. **Mechanical Uniformity**: Every element fading in simultaneously at the exact same linear duration, lacking physical momentum, stagger, or weight.
5. **Missing Physicality**: Static buttons with no press feedback (`active:scale-[0.98]`), and collapsible accordions that thrash layout geometry and drop frames.

`vibe-frontend-design` is an opinionated design-engineering skill for AI coding agents (Claude Code, Cursor, Windsurf, Codex). It replaces conversational ambiguity with concrete architectural parameters: **modular typography scales (1.25 ratio), 4-tier surface tokens, tactile spring physics, asymmetric Bento Grids, zero-CLS layout primitives, and 12 production-grade code recipes.**

---

## Live Interactive Demo

This repository includes a zero-dependency, self-contained interactive playground: [`demo/index.html`](demo/index.html).

You can open it directly in any browser:
```bash
# macOS
open demo/index.html

# Linux
xdg-open demo/index.html

# Windows
start demo/index.html
```

### Components Demonstrated Live in `demo/index.html`:
- **Double-Layer Magnetic Button**: 1.5x influence radius, 14px body pull, 20px inner text displacement, physical spring recoil (`stiffness: 180, damping: 14`), automatic touchscreen fallback.
- **Dynamic Cursor Spotlight**: Real-time relative coordinates driving radial gradient reflections along 1px hairline borders.
- **3D Perspective Tilt Card**: Cursor-driven spatial rotation with true Z-axis layer elevation (`translateZ`).
- **Decrypted Scramble Text**: High-frequency pseudorandom character rolling settling left-to-right into resolved text.
- **Zero-Layout-Thrashing Accordion**: Pure CSS Grid (`grid-template-rows: 0fr -> 1fr`) expanding at 60fps without JavaScript `scrollHeight` measurements.
- **1:1 Blueprint Shimmer Skeleton**: Exact dimensional match eliminating Cumulative Layout Shift (CLS = 0).

---

## The Contrast: The Slop vs. The Craft

```
[The Slop: Generic AI Symmetrical 3-Card Layout]
+---------------+---------------+---------------+
|    Card 1     |    Card 2     |    Card 3     |
| (Equal Width) | (Equal Width) | (Equal Width) |
+---------------+---------------+---------------+
No hierarchy. No visual anchor. Monotonous rhythm.

[The Craft: Asymmetric Bento Grid Architecture]
+-------------------------------+---------------+
|                               | Stat Tile 01  |
|      HERO ANCHOR TILE         +---------------+
|     (2x2 Column Span)         | Stat Tile 02  |
|  Interactive Flow Canvas      +---------------+
|                               | Wide Feature  |
+-------------------------------+---------------+
Clear focal point. Varied density. Intentional eye flow.
```

### Technical Dimension Comparison

| Dimension | Generic AI Generation (The Slop) | vibe-frontend-design (The Craft) |
|---|---|---|
| **Layout Rhythm** | Symmetrical 3-column equal cards with no focal point | **Asymmetric Bento Grid**: 2x2 Hero Tile + secondary metric chips |
| **Surface & Color** | Raw `#000` with oversaturated neon glow blobs | **4-Level Surface Hierarchy**: Level 0 Canvas (`#08090C`) -> Level 3 Overlay, 1px subtle borders |
| **Motion Dynamics** | All elements fade in simultaneously with linear easing | **50ms Stagger Cascade**, physical spring damping (`stiffness: 180, damping: 14`) |
| **Tactile Press** | Flat hover color change, zero active press feedback | **Double-Layer Magnetic Button**, tactile press `active:scale-[0.98]` |
| **Typography Scale** | Loose default tracking, unconstrained measure (120ch+) | **Modular Scale 1.25**, tight headline tracking (`-0.02em`), 65ch measure limit |
| **CJK Typography** | Squeezed Latin/CJK characters, punctuation at line start | **0.25em Pangu spacing**, `text-wrap: pretty; line-break: strict` |
| **Perceived Perf** | Blank loading states, jarring content jumps on arrival | **1:1 Shimmer Skeleton Screen**, pure CSS zero-reflow accordion, **CLS = 0** |

---

## Core Systems & Mechanics

### 1. The Three Dials Configuration
Before writing any code, the agent locks three baseline dials derived from the user's intent:

```markdown
DESIGN_VARIANCE:  [1 - 10]  # 1 = Conservative Symmetry  -> 10 = Asymmetric Experimental Art
MOTION_INTENSITY: [1 - 10]  # 1 = Clean Static           -> 10 = Cinematic Spring Physics & Parallax
VISUAL_DENSITY:   [1 - 10]  # 1 = Gallery Negative Space -> 10 = Mission-Critical Data Density
```

- **Minimalist / B2B SaaS**: `VARIANCE: 6 / MOTION: 4 / DENSITY: 5`
- **Consumer Landing / Apple-Style**: `VARIANCE: 8 / MOTION: 6 / DENSITY: 4`
- **Creative Studio / Portfolio**: `VARIANCE: 9 / MOTION: 8 / DENSITY: 3`

### 2. The 8-Field Spec Prompt Architecture
Upgrades informal conversational prompts into deterministic engineering specifications:

```markdown
1. Role: Composite specialist (Information Architect + Design Engineer).
2. Goal: Single primary conversion action (e.g., install CLI, schedule demo).
3. Audience: Primary device, technical familiarity, scanning behavior.
4. Pages & Blocks: Section inventory from Hero to Footer.
5. Information Architecture: F-pattern eye tracking, primary vs secondary weights.
6. Design System: Surface tokens, color palette, modular typography scale.
7. Interactions & States: Hover, Active, Focus-visible, Loading, Empty, Error.
8. Acceptance Criteria: Zero horizontal overflow on 390px, WCAG AA contrast, CLS = 0.
```

---

## Production Code Recipes

All 12 recipes in [`references/code-recipes.md`](references/code-recipes.md) are self-contained, tested, and ready to deploy:

### Recipe 1: Double-Layer Magnetic Button (React + Framer Motion)
```tsx
import React, { useRef, useState } from "react";
import { motion } from "framer-motion";

export function MagneticButton({ children, className = "" }: { children: React.ReactNode; className?: string }) {
  const buttonRef = useRef<HTMLButtonElement>(null);
  const [pos, setPos] = useState({ x: 0, y: 0 });

  const handleMouseMove = (e: React.MouseEvent<HTMLButtonElement>) => {
    if (window.matchMedia("(pointer: coarse)").matches) return; // Touchscreen safety fallback
    if (!buttonRef.current) return;
    const { clientX, clientY } = e;
    const { left, top, width, height } = buttonRef.current.getBoundingClientRect();
    // 0.35 spring attraction factor
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
        animate={{ x: pos.x * 0.5, y: pos.y * 0.5 }} // Inner text parallax displacement
        transition={{ type: "spring", stiffness: 220, damping: 16 }}
        className="inline-flex items-center gap-2 pointer-events-none"
      >
        {children}
      </motion.span>
    </motion.button>
  );
}
```

### Recipe 2: Zero-Layout-Thrashing Accordion (Pure CSS Grid)
```css
/* Eliminates layout thrashing caused by JavaScript scrollHeight measurements */
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

### Recipe 3: Dynamic Cursor Spotlight Card
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

## Modular Knowledge Base Index

Adheres to Anthropic's progressive disclosure standard, keeping `SKILL.md` focused while organizing specialized depth into `references/`:

| File | Scope | Topics Covered |
|---|---|---|
| [`SKILL.md`](SKILL.md) | Master Blueprint | Design Read, The Three Dials, Anti-Slop 10 Prohibitions, 12-Point QA Matrix |
| [`references/visual-dictionary.md`](references/visual-dictionary.md) | Visual Encyclopedia | Bento Grid patterns, Split-Screen layouts, 5 visual styles, surface tokens |
| [`references/motion-dictionary.md`](references/motion-dictionary.md) | Motion Encyclopedia | 4-layer motion framework, stagger intervals (50ms), parallax rates, FLIP reordering |
| [`references/code-recipes.md`](references/code-recipes.md) | Code Recipes | 12 production-ready React + Tailwind + Framer Motion component implementations |
| [`references/prompt-cookbook.md`](references/prompt-cookbook.md) | Prompt Cookbook | 8-field spec prompt architecture, full-page SaaS & portfolio prompt templates |
| [`references/chinese-typography.md`](references/chinese-typography.md) | CJK Typography | Modular font scales, Pangu spacing (0.25em), negative tracking, line-breaking |
| [`references/archive-aesthetic.md`](references/archive-aesthetic.md) | Archive Aesthetic | Knolling orthogonal grids, diffuse softbox lighting, technical specimen stamps |
| [`references/design-engineering-qa.md`](references/design-engineering-qa.md) | Engineering QA | CSS z-index stacking context matrix, zero-CLS rules, GPU compositing checks |
| [`references/github-highstar-ecosystem.md`](references/github-highstar-ecosystem.md) | High-Star Ecosystem | Deep dive into shadcn/ui, Magic UI, Aceternity, cmdk, and sonner architectures |

---

## Installation & Quickstart

### Method 1: Global Installation in Claude Code (Recommended)
Clone directly into your global user skills directory to make it available across all workspaces:
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/shinewinsu/vibe-frontend-design.git ~/.claude/skills/vibe-frontend-design
```

### Method 2: Per-Project Installation
Install directly inside a specific repository:
```bash
mkdir -p .claude/skills
git clone https://github.com/shinewinsu/vibe-frontend-design.git .claude/skills/vibe-frontend-design
```

### Method 3: Cursor / Windsurf / Codex
Add the contents of `SKILL.md` into your `.cursorrules` or reference it directly in conversation:
> "Strictly follow the vibe-frontend-design specification and 8-field spec architecture to build this interface."

---

## Terminal Usage

In Claude Code, invoke the skill directly:
```bash
/vibe-frontend-design
```

Or invoke it via natural language:
> "Invoke the vibe-frontend-design skill. Use the 8-field spec architecture from prompt-cookbook.md to build a Linear-style dark monitoring dashboard."

**The Agent will automatically**:
1. Emit a one-line `Design Read` and lock `The Three Dials`;
2. Enforce Anti-Slop prohibitions, rejecting purple gradient blobs and symmetrical 3-card clichés;
3. Apply modular typography scales with negative tracking and 65ch line limits;
4. Pull battle-tested code directly from `code-recipes.md` for production delivery.

---

## Credits & Prior Art

- **Special Recognition: [Adrian Punk (@AdrianPunk115)](https://x.com/AdrianPunk115)**: The visual and motion dictionaries, 8-field prompt architecture, and archive aesthetic standards are grounded in Adrian Punk's viral series on X.
- **[Leon Lin / taste-skill](https://github.com/Leonxlnx/taste-skill)**: For pioneering the Anti-Slop philosophy, Design Read, and The Three Dials system.
- **[shadcn/ui](https://github.com/shadcn-ui/ui) & [Radix UI](https://github.com/radix-ui/primitives)**: The baseline standard for unstyled, accessible primitives.
- **[Magic UI](https://github.com/magicuidesign/magicui) & [Aceternity UI](https://github.com/aceternity/ui)**: For modern animated marketing components and 3D visual spectacle.
- **[DavidHDev / react-bits](https://github.com/DavidHDev/react-bits)**: Creative interactive animation patterns and decrypted text effects.
- **[Emil Kowalski](https://emilkowal.ski/) & [Paco Coursey](https://paco.me/)**: For defining the craft of interaction design, tactile desktop-grade web software, cmdk, vaul, and sonner.
- **[ibelick](https://github.com/ibelick)**: For background snippet craftsmanship and noise overlay textures.

---

## License

This project is licensed under the [MIT License](LICENSE).
