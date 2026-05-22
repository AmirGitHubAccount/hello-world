# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Running the project

No build step or server required. Open `index.html` directly in a browser:

```
# Windows — open in default browser
start "D:\Project\claude\Projects\Hello world\index.html"
```

Or drag-and-drop `index.html` onto any browser tab. The page is fully self-contained.

## Architecture

Everything lives in a single file: `index.html`. It has three sections that are tightly coupled:

- **CSS (`:root` block)** — design tokens (`--btn-bg`, `--page-bg`, `--radius`, etc.) drive all colors and spacing. Change values here to restyle globally.
- **HTML** — two elements matter: `#greeting` (the text, initially hidden via `opacity:0`) and `#greet-btn` (the trigger).
- **JS (`<script>` at bottom)** — the click handler re-triggers the CSS animation by removing `.visible`, forcing a reflow with `void el.offsetWidth`, then re-adding `.visible`. This is the intentional pattern for replaying a CSS animation without cloning the element.

## Key constraints

- **No frameworks, no build tools, no npm.** Keep it a plain file that works via `file://`.
- **Google Fonts (`Inter`) is the only external dependency** — it degrades gracefully if offline (falls back to `sans-serif`).
- **Animation replay** relies on the reflow trick (`void greeting.offsetWidth`). Do not replace it with `setTimeout(0)` — that is less reliable across browsers.
- **Color palette** lives in the `COLORS` array in the script. The `pickColor()` function prevents two consecutive identical colors; keep that invariant if adding/removing colors.
- **Responsive breakpoint** at `480px` reduces `#greeting` from `72px` to `52px`. Adjust both values together if resizing.
