# 🧠 Thinking Out of The Box — A Self-Development Article Page

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Responsive](https://img.shields.io/badge/Responsive-Design-brightgreen?style=for-the-badge)
![Dicoding](https://img.shields.io/badge/Dicoding-Submission-4285F4?style=for-the-badge)
![Score](https://img.shields.io/badge/Score-5%2F5_%E2%98%85-FFD700?style=for-the-badge)
![Learning Path](https://img.shields.io/badge/Frontend_Web-Learning_Path_Stage_1-orange?style=for-the-badge)
![Live Demo](https://img.shields.io/badge/Live_Demo-GitHub_Pages-222?style=for-the-badge&logo=githubpages)](https://salsabilarh.github.io/article-web-dicoding)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

> ⭐ **Final submission for "Belajar Dasar Pemrograman Web"** — Stage 1 of the *Frontend Web Learning Path* at Dicoding.
> A semantically structured, fully responsive article page built to be extended with JavaScript. **Perfect score 5/5** from the Dicoding review team.

---

## 📖 Table of Contents

- [Executive Summary](#executive-summary)
- [Key Features](#key-features)
- [Tech Stack](#tech-stack)
- [Architecture & Technical Approach](#architecture--technical-approach)
- [Installation & Local Usage](#installation--local-usage)
- [What I Learned](#what-i-learned)
- [License](#license)

---

## Executive Summary

This project is a self-development article page built **from scratch** using **pure HTML5 and CSS3** — no framework, no library, no shortcuts.

> 🎯 **The real objective:** Not simply producing a page that renders, but demonstrating a genuine understanding of **correct web fundamentals**:
> - A semantic element hierarchy that is machine-readable
> - A layout system that holds together at every screen size 📱💻🖥️
> - Well-organized code that can be extended cleanly in subsequent iterations 🔁

---

## Key Features

### Usability

| Feature | Description |
|---------|-------------|
| 🔝 **Sticky Navigation** | The `nav` element stays visible during scroll — users always have access to navigation without scrolling back to the top |
| 🔗 **In-Page Anchor Links** | A clickable table of contents jumps directly to the relevant section (`#cara1` through `#cara7`) |
| 📰 **Two-Column Layout** | Article content (main column) and author profile sidebar sit side by side on wide screens for comfortable reading |
| 👤 **Circular Profile Photo** | The sidebar displays a complete author identity with a circular image and a structured information table |

### Reliability

| Feature | Description |
|---------|-------------|
| 📱 **Fully Responsive** | Three distinct breakpoints: desktop (>900px), tablet (≤900px), and mobile (≤600px) — built with pure CSS Flexbox, not the brittle `float` technique |
| 🔄 **Universal CSS Reset** | `* { box-sizing: border-box; margin: 0; padding: 0; }` prevents cross-browser rendering inconsistencies before they occur |
| 🖼️ **Adaptive Images** | `width: 100%; object-fit: cover;` ensures images never overflow their container at any screen size |
| 🔤 **External Font Fallback** | `font-family: 'Source Serif Pro', Georgia, serif;` — if Google Fonts fails to load, the page remains fully readable through graceful degradation |

---

## Tech Stack

```
📁 Technologies
├── HTML5          — Semantic structure & content
└── CSS3
    ├── Flexbox         — Primary layout system (not Float)
    ├── Media Queries   — Two-breakpoint responsiveness
    ├── Position Sticky — Persistent navigation
    └── Transitions     — Hover micro-interactions on cards
```

**External Dependencies:**
- [Google Fonts](https://fonts.google.com/) — `Source Serif Pro` (editorial serif typeface)
- No npm packages, no build tools — opens directly in any browser

---

## Architecture & Technical Approach

### HTML5 Semantic Structure

The page uses HTML5 semantic elements throughout — not generic `<div>` containers. Every element is chosen based on its *meaning*, not its appearance:

```
<body>
├── <header>              ← Branding & navigation area
│   ├── .jumbotron        ← Hero section
│   └── <nav>             ← Navigation menu (sticky)
├── <main>                ← Primary flex container
│   ├── <div #content>    ← Main content area (flex: 3)
│   │   └── <article>     ← Each article point as a self-contained unit
│   └── <aside>           ← Secondary / author profile info (flex: 1)
│       └── <figure>      ← Image + semantically bound caption
└── <footer>              ← Copyright information
```

Semantic structure is a prerequisite for efficient **DOM Manipulation** down the line. A selector like `document.querySelector('article#cara3')` is far more reliable than depending on the positional order of anonymous `<div>` elements.

### Layout System: Flexbox Over Float

The two-column layout is built entirely with CSS Flexbox:

```css
/* Flex container — main layout */
main {
    display: flex;
    flex-wrap: wrap;   /* Automatically wraps to single column on small screens */
    gap: 30px;
}

#content { flex: 3; min-width: 260px; }  /* Article: ~75% of available space */
aside    { flex: 1; min-width: 250px; }  /* Sidebar: ~25% of available space */
```

`flex-wrap: wrap` combined with `min-width` is an *intrinsic* responsive mechanism — the layout collapses to a single column automatically when space runs out, without requiring a media query `if-else` condition. Media queries are reserved for targeted typography and spacing adjustments specific to each breakpoint.

---

## Installation & Local Usage

No build tools, local server, or installation of any kind required.

**Option 1 — Open directly:**
```bash
# Clone the repository
git clone https://github.com/salsabilarh/article-web-dicoding.git

# Enter the project folder
cd article-web-dicoding

# Open index.html in your browser
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

**Option 2 — Via VS Code Live Server:**
1. Install the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension in VS Code
2. Right-click `index.html` → **"Open with Live Server"**
3. The browser will open at `http://127.0.0.1:5500`

**Project structure:**
```
article-web-dicoding/
├── index.html          ← Main entry point
├── style.css           ← All styling (single file, organized by section)
└── assets/
    ├── profile.jpg     ← Author profile photo
    ├── books.jpg
    ├── alone.jpg
    ├── do.png
    ├── world.png
    ├── kreatif.jpg
    ├── critical.jpg
    └── design-thinking.png
```

---

## What I Learned

### 1. Clean Code Is About Maintainability, Not Aesthetics

The CSS is organized into named blocks with consistent section comments (`/* ===== HEADER ===== */`, `/* ===== NAVIGATION ===== */`) rather than a single monolithic stylesheet. This is not about appearance — it is about **maintainability**: any developer (or yourself six months later) can locate and modify a specific section in seconds.

The same discipline applies to HTML: the `alt` attribute on every `<img>` is not a formality — it reflects the understanding that web code is consumed not only by humans, but by screen readers, web crawlers, and parsers of all kinds.

### 2. CSS Flexbox as the Foundation of Modern Layout Thinking

Understanding `flex`, `flex-wrap`, `gap`, and `min-width` deeply — not just copying them — changes how layout is approached entirely. Flexbox *declares intent* ("these elements share space proportionally") rather than *instructing position* as float does. This declarative mindset closely mirrors how modern frameworks like React and Vue manage state: describe the desired outcome, let the system figure out the mechanics.

### 3. Responsiveness as Behavior, Not an Afterthought

Using `flex-wrap` + `min-width` as an *intrinsic* responsive mechanism before reaching for media queries means a layout that works correctly across a wide range of conditions with minimal code. This is the principle of **Progressive Enhancement** in practice: start with the most fundamental, correct foundation — then layer specific adjustments on top.

### 4. Semantic HTML as the Contract for API Consumption

A semantically structured DOM is an **implicit contract** that simplifies every layer built on top of it. When consuming a RESTful API later — say, an `/api/articles` endpoint returning a JSON array — JavaScript only needs to render data into the `<article>` template that already exists. The separation of **structure** (HTML), **presentation** (CSS), and **behavior** (JS) practiced here is a direct implementation of the Separation of Concerns principle — the same principle that governs clean backend architecture.

---

## License

This project was built as a Dicoding course submission and is open for educational use.

---

*Submission: Belajar Dasar Pemrograman Web — Stage 1 of Frontend Web Learning Path, Dicoding 2026*
*Reviewed Score: ⭐ 5/5 — Perfect*