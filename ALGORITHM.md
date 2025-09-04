# ALGORITHM (Pseudocode)

DATA MODEL
- tokens[]: {{ id, name, symbol, icon, mcap_usd:number, change_pct:number }}

LOAD DATA
- Try fetch('data/tokens.json'). If it fails (file://), use window.FALLBACK_TOKENS.

UTILS
- compactUSD(n) -> '$' + compact string with B/M/K
- pctColorClass(p) -> 'gain' | 'loss'
- hashToLane(name, lanes) -> deterministic 0..lanes-1

PAGE 1 — BOARD
- State: sortKey ('mcap_desc'|'change_desc'|'name_asc'), filter ('all'|'gainers'|'losers')
- Filter list, sort list, render cards.
- Card includes: icon, name, MCAP, signed %; class uses pctColorClass.
- Controls update state and re-render.
- Responsive grid: repeat(auto-fit, minmax(220px, 1fr)).

PAGE 2 — MOON RACE
- State: target (default 1e7). Buttons set target & aria-pressed.
- lanes = 6..12 based on width.
- For each token:
  ratio = clamp(mcap_usd/target, 0..1)
  y = ratio * 100 (% from bottom)
  lane = hashToLane(name, lanes)
  x = (lane + .5)/lanes * 100 (% of width)
  size = map sqrt(mcap) -> [36, 72] px
  bubble classes: pctColorClass, add 'reached' if mcap ≥ target
- Render tooltips on hover/focus.
- Leaderboard: sort by mcap desc; top3 in medal cards; rest as list.

ACCESSIBILITY
- Buttons with aria-labels; visible focus; tooltips use role="tooltip".
- Color never the sole channel; signs and text show gain/loss.
