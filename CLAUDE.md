# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static single-page website for **Bistro Lumiere**, a fictional French bistro restaurant. The site is in Japanese and has no build system — it is plain HTML, CSS, and JavaScript opened directly in a browser.

## File Structure

- `index.html` — The entire page markup. Sections in order: `header` (nav + hamburger + dark mode toggle), `#home` (hero), `#about`, `#menu`, `#gallery`, `#contact` (reservation form), `footer`.
- `style.css` — Referenced but not yet created. Must be created to style the page.
- `script.js` — Referenced but not yet created. Must handle dark mode toggle, hamburger menu, and scroll animations.

## Running the Site

No build step. Open `index.html` directly in a browser:

```bash
open index.html          # macOS
xdg-open index.html      # Linux
```

Or use a simple local server:

```bash
python3 -m http.server 8080
```

## Architecture & Conventions

**Fonts:** Google Fonts — `Playfair Display` (headings, English display text) and `Noto Sans JP` (Japanese body text).

**Animations:** Elements use CSS classes `fade-in` and `fade-up`, with staggered timing via `delay-100`, `delay-200`, `delay-300`. JavaScript should add an `is-visible` (or equivalent) class when elements enter the viewport via IntersectionObserver.

**Dark mode:** The `#theme-toggle` button toggles dark/light theme. Convention should use a `data-theme` attribute on `<html>` or a `.dark` class on `<body>`.

**Layout helpers:** `.container` constrains max-width and centers content. `.grid-2` is a two-column layout used in the About and Contact sections.

**Mobile nav:** `.hamburger` button toggles the `.nav-list` visibility on small screens.

**Menu cards:** `.menu-card` elements each have an `.menu-icon` (emoji), heading, dish name, `.price`, and `.menu-desc`.

**Gallery:** `.gallery-item` elements have an `.img-placeholder` div (image not yet provided) and a `.gallery-overlay` with caption text on hover.
