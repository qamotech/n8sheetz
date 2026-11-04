# 📊 N8Sheetz

**▶️ Live: https://qamotech.github.io/n8sheetz/**

A single-file, offline-capable spreadsheet app — dark, high-contrast, virtualized grid (26 columns × 1,000 rows), formulas, charts, snapshots, and a command palette. No build step, no dependencies: open `N8Sheetz.html` in any browser.

**Data:** saves automatically to the browser's `localStorage` (`n8sheetz_state`). Use **File → Save As (.json)** for a portable workbook backup; **File → Open (CSV)** and **Import Workbook (.json)** bring data back in.

## v2.4 (Nov 4, 2026)

- 📚 **Template library rebuilt: 75 → 40.** Cut 35 primitive/duplicate presets (dup budgets, novelty trackers, thin calculators). Every survivor was rewritten as a real working table: 5–10 rows of realistic sample data (Arc Beverage inventory SKUs, a Clark Family Projects invoice, homeschool grades/lessons, mileage at the IRS rate), working formulas throughout (totals, averages, letter grades via IF, amortization balances, pipeline sums), status dots 🟢🟡🔴, ✅ trackers, and progress-bar cells. Average template depth went from 2.7 rows to 7+. Start screen now reads 'Search 40 templates…' and previews reflect the new data.

## v2.3 (Nov 4, 2026)

- 💎 **New logo + 40 UI/effects/buttons/menus upgrades.** Logo: emerald gem with spreadsheet-grid facets and a bold 8, gold trim on a deep-space navy tile (same family as the 1poly mark) — top bar, start-screen hero, and favicon. Plus: animated menus, toast progress bars, modal blur/pop, template-card shine, crosshair row/column bands, sheet-tab context menu (rename / duplicate / delete / tab colors, double-click rename), Insert Date/Time/Checkbox (click to toggle ☑)/Symbols, Text to Columns, Shuffle Rows, Banded Rows, Clear Formatting, Go to Last Cell, Gridlines + Crosshair toggles, Cell Inspector, Shortcuts sheet, status-bar zoom cycler + saved-time indicator, ⌂ A1 return floater, and document title that follows the active sheet. Old duplicate save indicator retired.

## v2.2.1 (Nov 3, 2026)

- 🎯 **Highlight fix.** Drag hit-testing now measures real cell positions (the old math assumed stock column widths, so at zoom levels or custom column widths the highlight landed on different cells than your finger). Selection is now unmistakable: brighter range tint, a solid **perimeter outline** around the range, **row + column headers light up** for the selected span, and the current cell is the brightest one in the range.

## v2.2 (Nov 3, 2026)

- ⚡ **Selection smoothness pass — 24 improvements.** The big one: grid `scroll-behavior: smooth` and an 82ms-per-render selection painter made every drag animate behind the pointer. Selection now paints in ~2ms (flat cost, visible-cells-only sweep), moves are rAF-coalesced with geometry hit-testing and pointer capture, edge auto-scroll runs on its own rAF loop (hold at the edge and the selection keeps extending), stats are computed from stored data and throttled, and native scroll/selection ghosts are suppressed. New: Tools → ⚡ Selection Perf Check.

## v2.1 (Nov 3, 2026)

- 🖼️ **Preset previews upgraded** — all 75 start-screen template cards now show a true miniature of the template inside (real headers + real first rows, category color, column/row/formula counts, dark theme) instead of the old generic random-dash grid; the template search box actually filters now.

## v2 upgrade (Nov 3, 2026)

- 🐛 **Multi-cell selection fixed** — the old build had two competing keyboard handlers (plain arrow keys moved the active cell *two* steps) and no Ctrl/Cmd-click handling at all (Ctrl+click destroyed the current range). Selection is now one pointer + keyboard model: drag, Shift+click, Shift+arrows with a true anchor, **Ctrl+click / Ctrl+drag disjoint ranges**, row/column header drag, two-stage Ctrl+A, and a touch **Range mode** for phones.
- 🧰 **Menus & tools overhaul** — 9 fake filler menus (hundreds of "Not implemented" items) removed; the 7 real menus (File, Edit, Format, Data, Tools, Insert, View) are grouped with section headings, shortcut hints, viewport-clamped dropdowns, and ≥44px touch targets. A labeled **Quick Tools bar** (Go to / Select / Numbers / Cells / Data / Formula / Sheet) puts the everyday tools one tap away.
- 🔢 **40 enhancements** — working decimals +/−, thousands separator, borders, text wrap, fill series, sort, dedupe rows, drop blank rows, trim, case transforms, transpose, join, quick Σ/Avg/Count/Min/Max formulas, a VLOOKUP/COUNTIF/SUMIF formula builder, freeze panes at the active cell, print-selection, selection CSV export, copy-values (TSV), range-aware status stats, and unified Find & Replace — every edit undoable (Ctrl+Z) and autosaved.
- ✅ Verified with automated headless-browser tests: selection model, formulas, formatting, freeze, export, and original↔upgraded saved-workbook compatibility in both directions — zero console errors at 390 / 768 / 1280 px.
