# 📊 N8Sheetz

**▶️ Live: https://qamotech.github.io/n8sheetz/**

A single-file, offline-capable spreadsheet app — dark, high-contrast, virtualized grid (26 columns × 1,000 rows), formulas, charts, snapshots, and a command palette. No build step, no dependencies: open `N8Sheetz.html` in any browser.

**Data:** saves automatically to the browser's `localStorage` (`n8sheetz_state`). Use **File → Save As (.json)** for a portable workbook backup; **File → Open (CSV)** and **Import Workbook (.json)** bring data back in.

## v2.1 (Nov 3, 2026)

- 🖼️ **Preset previews upgraded** — all 75 start-screen template cards now show a true miniature of the template inside (real headers + real first rows, category color, column/row/formula counts, dark theme) instead of the old generic random-dash grid; the template search box actually filters now.

## v2 upgrade (Nov 3, 2026)

- 🐛 **Multi-cell selection fixed** — the old build had two competing keyboard handlers (plain arrow keys moved the active cell *two* steps) and no Ctrl/Cmd-click handling at all (Ctrl+click destroyed the current range). Selection is now one pointer + keyboard model: drag, Shift+click, Shift+arrows with a true anchor, **Ctrl+click / Ctrl+drag disjoint ranges**, row/column header drag, two-stage Ctrl+A, and a touch **Range mode** for phones.
- 🧰 **Menus & tools overhaul** — 9 fake filler menus (hundreds of "Not implemented" items) removed; the 7 real menus (File, Edit, Format, Data, Tools, Insert, View) are grouped with section headings, shortcut hints, viewport-clamped dropdowns, and ≥44px touch targets. A labeled **Quick Tools bar** (Go to / Select / Numbers / Cells / Data / Formula / Sheet) puts the everyday tools one tap away.
- 🔢 **40 enhancements** — working decimals +/−, thousands separator, borders, text wrap, fill series, sort, dedupe rows, drop blank rows, trim, case transforms, transpose, join, quick Σ/Avg/Count/Min/Max formulas, a VLOOKUP/COUNTIF/SUMIF formula builder, freeze panes at the active cell, print-selection, selection CSV export, copy-values (TSV), range-aware status stats, and unified Find & Replace — every edit undoable (Ctrl+Z) and autosaved.
- ✅ Verified with automated headless-browser tests: selection model, formulas, formatting, freeze, export, and original↔upgraded saved-workbook compatibility in both directions — zero console errors at 390 / 768 / 1280 px.
