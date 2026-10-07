# FDS Inline Edit

Working prototype for inline editing in the Frontend Data Set (table view) — [LPD-9102](https://liferay.atlassian.net/browse/LPD-9102).

No build step, no server. Open `index.html` directly in a browser.

## What's here

One live "Products" table with the FDS field renderers, all of them actually interactive:

| Column | Renderer | How it edits |
| --- | --- | --- |
| Image | Image | Panel with preview and file chooser (PNG, JPG, GIF or WebP, up to 1 MB) |
| Name | Default | Inline text input, required, max 60 characters |
| Catalog | Default (select) | Option list |
| Type | Label | Option list rendering labels |
| Status | Status | Option list rendering status labels |
| Link | Link | Inline input, must be a valid URL |
| Quantity | Quantity selector | Inline input with − / + steppers, whole number 0–999 |
| Published | Boolean | Toggle |
| Expire Date | Date | Calendar, or type the date; can't be in the past |
| Details | Action link | Not editable inline, shows what it does |

Some cells are locked to show the read-only state: a lock appears on hover and clicking explains why.

## One validation model

Every field follows the same rules, so behavior is predictable:

- **Edit, then confirm.** Free-form fields (text, link, quantity, date, image) work on a draft. ✓ or Enter saves it, ✕ or Escape cancels and restores the previous value.
- **Invalid never saves.** A failed check keeps the editor open, turns the cell red and shows the reason in a tooltip (also announced to screen readers). Nothing is written until the draft is valid.
- **Success is a short flash.** A saved value flashes green with a check, then the cell goes back to idle. Idle cells are never tinted.
- **Picking is committing.** Option lists and the toggle can't hold an invalid draft, so choosing a value saves it straight away with the same green flash.
- **One editor at a time.** Opening another cell discards an unsaved draft; clicking outside a calendar, list or image panel cancels it.

Keyboard support throughout: Enter/Escape to save/cancel, ↑/↓ to move between rows, arrow keys through the calendar and option lists.

## Status

Actively evolving — more interaction refinements are still being explored.
