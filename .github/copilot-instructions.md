# Copilot instructions for this codebase

## Project overview
- Static multi-page site: plain HTML/CSS with a small JS helper for page transitions (no build system or dependencies).
- Pages follow the “A - *.html” pattern and each page links a matching “B - *_styles.css” plus shared styles.
- Assets are local: images in Images/, fonts in Fonts/ (registered via CSS custom properties).

## Architecture and key files
- Global navigation + fade transitions:
  - Shared nav styles and page fade animation in [B - navstyles.css](../B%20-%20navstyles.css).
  - Click interception + fade-out handled by [page-transition.js](../page-transition.js).
- Fonts setup: [B - fonts.css](../B%20-%20fonts.css) defines `--font-body` and `--font-display` used across pages.
- Page examples:
  - Landing hero in [A - index.html](../A%20-%20index.html) styled by [B - styles.css](../B%20-%20styles.css).
  - Group overview section in [A - circle.html](../A%20-%20circle.html) styled by [B - circle_styles.css](../B%20-%20circle_styles.css).
  - Members list structure in [A - members.html](../A%20-%20members.html) styled by [B - members_styles.css](../B%20-%20members_styles.css).

## Project-specific conventions
- Keep the “A -” / “B -” filename pairing when adding new pages or stylesheets.
- Each page repeats the same `<nav>` markup; set the current link with `class="active"` to trigger nav emphasis.
- Always include [B - fonts.css](../B%20-%20fonts.css) and [B - navstyles.css](../B%20-%20navstyles.css) on every page.
- Page-specific layout/styles live only in the matching stylesheet (avoid mixing page styles into nav or fonts files).

## Editing guidance
- Use relative asset paths like `Images/...` and `Fonts/...` (no CDN references used here).
- Preserve the page-transition behavior: keep the `page-fade-out` class and the `body` fade-in animation in [B - navstyles.css](../B%20-%20navstyles.css) alongside the script in [page-transition.js](../page-transition.js).
- Prefer semantic sections (`<main>`, `<section>`, lists) and match existing structure when adding new content.
