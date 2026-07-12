---
name: verify
description: Build this Jekyll site and visually verify layout/CSS changes headlessly with Playwright Chromium.
---

# Verify a change on this site

1. Build: `bundle exec jekyll build` (Ruby/Jekyll already installed; output in `_site/`).
2. Serve: `cd _site && python3 -m http.server 8123 &` (absolute links like `/assets/...` break under `file://`, so a server is required).
3. Drive: Playwright for Python is installed (`python3 -m pip install --user playwright` + `python3 -m playwright install chromium` if missing). Load `http://localhost:8123/<page>.html`, `page.evaluate` with `getBoundingClientRect()` to measure layout, `page.locator("main").screenshot()` for the paper.

Gotchas:
- Photo posts open with a full-viewport `<figure>` hero; a viewport screenshot at the top shows only that. Screenshot the `main` locator (or scroll to it) to see the paper.
- Wait ~1.5s after load for web fonts before measuring text-driven widths.
- Non-production builds highlight `:lang(en)` text in the accent color (dev-only CSS in `default.html`) — expected, not a bug.
- Key breakpoint: 52rem (832px). Test both a wide viewport (e.g. 1280) and a narrow one (e.g. 600).
- The paper (`main`) is `width: fit-content`; children with percentage widths don't contribute to it (they fall back to intrinsic size during fit-content sizing). Elements that must not set the paper's width use `width: 0; min-width: 100%` (see footer and `.embedded-video`).
- Safari WebDriver is not enabled on this machine and there is no Node.js — use the Python Playwright route.
