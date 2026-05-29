# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a static single-page website for **Bistro Lumiere** (隠れ家ビストロ), a fictional French bistro in Tokyo. The site is Japanese/English bilingual and requires no build step — it is plain HTML, CSS, and JavaScript.

## Local Development

Open directly in a browser or serve with a local HTTP server to avoid CORS issues with fonts:

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

No package manager, bundler, or test runner is used.

## Architecture

`index.html` is the single entry point. It references two files that must exist alongside it:

- **`style.css`** — all styling (not yet created as of initial commit)
- **`script.js`** — all interactivity (not yet created as of initial commit)

### Page sections (in order)

| Section ID | Purpose |
|---|---|
| `#home` (`.hero`) | Full-bleed hero with CTA button |
| `#about` | Two-column layout (text + image placeholder) |
| `#menu` | Four-card grid of signature dishes |
| `#gallery` | Three-item image grid with overlay captions |
| `#contact` | Two-column layout: store info + reservation form |

### JavaScript features expected by the HTML

The `index.html` already wires up these behaviors that `script.js` must implement:

- **Dark mode toggle** — `#theme-toggle` button with `.icon` span (shows 🌙/☀️)
- **Hamburger menu** — `.hamburger` element for mobile nav
- **Scroll animations** — elements carry `fade-in`, `fade-up`, and `delay-{100,200,300}` classes; likely driven by `IntersectionObserver`

### CSS layout classes used in HTML

`grid-2`, `menu-grid`, `gallery-grid` — CSS Grid containers defined in `style.css`.

### Fonts

Loaded from Google Fonts: `Noto Sans JP` (Japanese body text) and `Playfair Display` (English headings).
