# VR Island · Fox Creator

A responsive landing page built from Figma to pixel accuracy, verified by
measurement at every breakpoint rather than by eye.

**Live:** https://kurejas.github.io/vr-island/

## Breakpoints

| | design width | verified page height |
|---|---|---|
| Desktop | 1728 | 18639 |
| Tablet | 1194 | 15970 |
| Mobile | 402 | 11872 |

No section deviates from the Figma frame by more than 2px.

## Build notes

Plain HTML and CSS — no framework, no build step. Open `index.html`.

- **Cap-height to baseline trim** — `text-box-trim` where supported, with a
  Capsize `::before`/`::after` fallback, so CSS block heights equal Figma's.
- **Side-bearing trim** — negative margins pull the opening glyph's bearing
  off and give it back on the right, so ink meets the edge without changing
  the measure or the line breaks.
- **No scaling** — fixed px per breakpoint. Containers flex, contents don't.
- **Layout grid overlay** — press <kbd>G</kbd> to toggle a live copy of the
  Figma layout grids (red columns, green spacer rhythm).

## Stack

- Helvetica Now Display (Monotype, licensed) — subset to `.woff2` per weight
- Images WebP, with AVIF where it wins; video H.264 `yuv420p` + `faststart`
- Deferred posters and `IntersectionObserver` autoplay; nothing loads until
  it approaches the viewport
