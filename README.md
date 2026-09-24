# FDS Inline Edit

Working prototype for inline editing in the Frontend Data Set (table view) — [LPD-9102](https://liferay.atlassian.net/browse/LPD-9102).

No build step, no server. Open `index.html` directly in a browser.

## What's here

One live "Products" table where every field type is actually interactive, not a static mockup:

- **Name** — click to edit as plain text. Validates on save and on tab-away; a fixed value can't be left empty.
- **Catalog** — click to open a real option list; picking a value commits immediately.
- **Status** — same picker pattern as Catalog, rendering colored status labels instead of plain text.
- **Modified Date** — click to open a real calendar. Browsing days previews the value live; clicking away confirms it, Escape discards it.

Keyboard support throughout: Enter/Escape to save/cancel, arrow keys to move between cells or through a calendar/list.

## Status

Actively evolving — more field types and interaction refinements are still being explored.
