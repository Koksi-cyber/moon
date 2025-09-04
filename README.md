# Moonboard Webpages

Two static pages that replicate the provided screenshots:
- **index.html** — Token board / heatmap.
- **moon-race.html** — Moon Race visualization with leaderboard.

## How to open
Just double‑click the HTML files (no build or server required).

> Note: Some browsers block `fetch()` from `file://`. The scripts include a built‑in fallback dataset (`FALLBACK_TOKENS`) so the pages still work offline. If you prefer to load `data/tokens.json` explicitly, open the folder with a tiny static server (e.g., `python -m http.server`) — optional.

## Features
- Mobile‑first responsive layout (360px → 1440px+)
- Sorting & filtering on the board
- “Race to …” targets (100K → 1B)
- Tooltips on bubbles; keyboard focus shows tooltip too
- Accessible focus ring, labeled buttons, color contrast on dark theme

## Files
```
/index.html
/moon-race.html
/css/styles.css
/js/main.js
/data/tokens.json
/assets/default-token.svg
/UI_PLAN.md
/ALGORITHM.md
/QA_REPORT.md
```
