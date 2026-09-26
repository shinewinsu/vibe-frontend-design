# 中文字体与现代排版设计全维指南 (Chinese Typography & Editorial Guide)

> 本指南整合了 Adrian Punk（@AdrianPunk115）的《2026 中文字体 AI 提示词指南》、《40 种杂志封面英文字体图鉴》以及现代中西文混排规范（W3C 需求与苹果/大厂字体排版标准）。  
> 专为解决现代 Web 前端中“中文字体发虚”、“中西文混排断裂”、“大标题散漫无力”、“标点挤压与避头尾”等核心设计与工程痛点。

---

## 目录
1. [中文字阶与行高黄金比例 (Font Sizes & Line Heights)](#1-中文字阶与行高黄金比例-font-sizes--line-heights)
2. [中西文混排与排版间隔规则 (CJK & Latin Pairing Rules)](#2-中西文混排与排版间隔规则-cjk--latin-pairing-rules)
3. [现代主流前端中文字体栈 (Production Font-Family Stacks)](#3-现代主流前端中文字体栈-production-font-family-stacks)
4. [大标题排版张力与字效 (Heading Treatments & Tracking)](#4-大标题排版张力与字效-heading-treatments--tracking)
5. [标点符号挤压与避头尾处理 (Punctuation & Line Breaking)](#5-标点符号挤压与避头尾处理-punctuation--line-breaking)
6. [排版工具与 CSS 样式渲染实操 (Markdown to Clean HTML)](#6-排版工具与-css-样式渲染实操-markdown-to-clean-html)

---

## 1. 中文字阶与行高黄金比例 (Font Sizes & Line Heights)

中文属于方块表意文字，字符视觉重心高、无上伸下延部分，因而**必须比西文字体使用更大的行高（Line-height）**，否则极易挤成一团。

### 1.1 中文模块化字阶表（基准比例 1.25）
| 级别 | 字号 (px) | 推荐行高 (Line-height) | 字重 (Font-weight) | 视觉用途 |
|---|---|---|---|---|
| **Display Mega** | `48px - 64px` | `1.15 - 1.20` | `700 (Bold) / 800 (ExtraBold)` | Hero 首屏大标语 |
| **Heading 1** | `32px - 36px` | `1.25 - 1.30` | `700 (Bold)` | 页面主标题 |
| **Heading 2** | `24px - 28px` | `1.30 - 1.35` | `600 (SemiBold)` | 板块/模块级标题 |
| **Heading 3** | `18px - 20px` | `1.40 - 1.45` | `600 (SemiBold)` | 卡片、列表项标题 |
| **Body Large** | `16px` | `1.65 - 1.75` | `400 (Regular)` | 引导性引言、重点段落 |
| **Body Base** | `14px - 15px` | `1.65 - 1.75` | `400 (Regular)` | 界面通用正文 |
| **Caption** | `12px - 13px` | `1.50` | `400 (Regular)` | 辅助说明、时间戳 |
| **Micro Badge** | `11px` | `1.00` | `500 (Medium)` | 状态药丸胶囊徽章 |

---

## 2. 中西文混排与排版间隔规则 (CJK & Latin Pairing Rules)

中文字符与英文字母、数字直接紧贴会导致视觉拥挤，破坏节奏：

### 2.1 盘古之白（中西文之间预留微小间隙）
- **规范**：中文字符与英文字母/阿拉伯数字之间，应保持约 `0.25em` 的视觉空白（即“盘古之白”）。
- **现代 CSS 解决方案**：
  现代浏览器原生支持 `text-autospace`（或 `font-feature-settings: "palt"`）：
  ```css
  body {
    /* 现代浏览器自动在中西文之间插入微小空白 */
    text-autospace: normal;
    text-spacing-trim: space-all;
  }
  ```
- **手动输入准则**：在 Markdown 文案或静态文案中，严格保持英文单词、数字与中文汉字之间手敲一个半角空格（例如：`支持 60fps 丝滑渲染，延迟低于 12ms`）。

### 2.2 专有名词与数字对齐
- 数字推荐开启等宽数字（Tabular Figures），尤其是在仪表盘、价格表和排行数据看板中：
  ```css
  .tabular-nums {
    font-variant-numeric: tabular-nums;
  }
  ```

---

## 3. 现代主流前端中文字体栈 (Production Font-Family Stacks)

不同操作系统对中文字体的渲染各有偏好，必须提供**免下载、原生加速、平滑回退**的系统字体栈：

### 3.1 极简现代无衬线中文字体栈（推荐默认）
```css
--font-sans:
  /* 西文优先，使用高品质几何字体 */
  "Inter", "Geist", -apple-system, BlinkMacSystemFont,
  /* 苹果系统中文：苹方 */
  "PingFang SC", "PingFang TC",
  /* Windows 系统中文：微软雅黑 */
  "Microsoft YaHei", "Source Han Sans SC", "Noto Sans SC",
  /* 兜底 */
  sans-serif;
```

### 3.2 瑞士/典雅人文衬线中文字体栈（用于高端杂志/报告风）
```css
--font-serif:
  /* 西文优雅衬线 */
  "Newsreader", "Playfair Display", "Georgia",
  /* 苹果系统中文：宋体/楷体 */
  "Songti SC", "STSong",
  /* Windows 系统中文：思源宋体/中易宋体 */
  "Source Han Serif SC", "Noto Serif SC", "SimSun",
  serif;
```

### 3.3 终端/代码块等宽字体栈
```css
--font-mono:
  /* 西文等宽 */
  "Geist Mono", "JetBrains Mono", "SF Mono", "Fira Code",
  /* 中文等宽 */
  "PingFang SC", "Microsoft YaHei",
  monospace;
```

---

## 4. 大标题排版张力与字效 (Heading Treatments & Tracking)

### 4.1 紧凑字距与字偶间距 (Optical Kerning & Tight Tracking)
- **大标题字距**：汉字大标题字号越大，字心视觉外溢越明显，字间距若为默认值会显得松垮无力。
- **参数标准**：
  - 32px 以上大标题：设置 `letter-spacing: -0.02em` 至 `-0.025em`；
  - 14px 正文内容：保持 `letter-spacing: 0`；
  - 12px 小写徽章或全大写英文：反向增加字距 `letter-spacing: 0.05em`。

### 4.2 渐变字效与微弱轮廓光 (Gradient Text with Subtitle Glow)
```css
/* 高端现代标题渐变字 */
.text-hero-gradient {
  background: linear-gradient(180deg, #FFFFFF 0%, rgba(255, 255, 255, 0.7) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  text-shadow: 0 0 40px rgba(255, 255, 255, 0.1);
}
```

---

## 5. 标点符号挤压与避头尾处理 (Punctuation & Line Breaking)

中文标点符号（如逗号、句号、引号）常因占满全角宽度造成行末空白过大或行首出现句号：

### 5.1 标点避头尾法则 (Line Breaking Rules)
- **禁止在行首出现的标点**：`，`、`。`、`、`、`；`、`：`、`！`、`？`、`）`、`”`、`』`、`》`；
- **禁止在行末出现的标点**：`（`、`“`、`『`、`《`。
- **CSS 强化声明**：
  ```css
  .cjk-content {
    line-break: strict;
    word-break: break-word;
    text-wrap: pretty; /* 现代防孤字孤行排版 */
  }
  ```

---

## 6. 排版工具与 CSS 样式渲染实操 (Markdown to Clean HTML)

Adrian Punk 在制作《公众号/Web Markdown 排版工具》中总结的纯前端排版核心要诀：
1. **引用块 (Blockquote)**：采用左侧 `3px solid var(--accent)`，背景填充 `rgba(..., 0.03)`，内部首行文字缩进与字阶微小收敛（`text-sm leading-relaxed text-zinc-400`）。
2. **行内代码 (Inline Code)**：带有 `px-1.5 py-0.5 rounded-md` 的微小胶囊，字体略小 0.5px，背景轻微提亮，杜绝突兀的高亮色块。
3. **代码块 (Code Block)**：深炭黑卡片底，顶部带 macOS 风格三色圆点（红/黄/绿），右侧带“一键复制”交互按钮，自动水平滚动。
