# QA REPORT (What was verified in code)
- **Responsive breakpoints:** layout rules for 360px, 768px, 1024px, 1440px with grid/flex-based flow. No fixed widths that cause overflow.
- **No horizontal scroll:** containers use `inset` and `grid` with `minmax()`; content wraps.
- **Keyboard:** All interactive items are buttons or focusable anchors; global `:focus-visible` ring; tooltips also appear on focus.
- **Contrast:** Text on dark panels uses `#cfe8ff` / `#dfe9ff`; gain/loss hues have strong contrast; backgrounds keep opacity low.
- **Performance:** Single stylesheet and script; tiny SVG icon; fallback dataset avoids extra network calls.
- **Graceful errors:** If `tokens.json` fails to load due to `file://` security, app falls back to embedded data.
- **Edge cases:** Empty filter state shows a friendly message; MCAP > target clamps bubble to top with a pulse.

> Note: I cannot physically open a browser in this environment. The code is structured to be standards‑compliant and should render correctly when you open the HTML files on your machine. If you spot any hiccups, tell me the screen size and I’ll adjust immediately.
