# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a GitBook-based personal daily journal and productivity tracker. There are no build steps, tests, or linters — it is a content repository rendered by GitBook.

## Repository Structure

- `README.md` — The GitBook landing page, which doubles as the template for new daily entries.
- `SUMMARY.md` — GitBook's table of contents. **Every new page must be registered here** or it won't appear in GitBook's navigation.
- `this-week/` — Daily entries for the current week. Files are named `{DD}-{mmm}-{day}.md` (e.g., `15-aug-mon.md`).
- `archive/{YYYY}/{month}/` — Past entries, moved here when a week ends. Section index pages (`README.md`) exist at the year and month level.

## Content Conventions

### Daily page structure

Each daily entry follows this fixed structure (copy from `README.md` as the template):

1. **Today's stuff** — A GitBook table with a checkbox column, a `Type` select column (`meeting` | `task`), and an `Action` text column.
2. **Notes & ideas** — One `<details>/<summary>` block per item from the table above.
3. **How was the day?** — Two collapsible sections: `🧠 Mood tracking` and `💡 Observations`.
4. **Habit tracking table** — A `data-type="rating"` table rating Sleep, Work/life balance, Creativity, and Fitness (max 5).

### GitBook-specific syntax

- Callout blocks: `{% hint style="info" %}…{% endhint %}`
- Checkbox cells: `<th data-type="checkbox">` / `<td>false</td>` (or `true`)
- Select cells: `<th data-type="select">` with `<option>` children; values in `<td>` use `<span data-option="…">…</span>`
- Rating cells: `<th data-type="rating" data-max="5">`

### SUMMARY.md maintenance

When adding or archiving pages, update `SUMMARY.md` to match. The format mirrors the directory layout:

```markdown
## This week
* [15 Aug - Mon](this-week/15-aug-mon.md)

## Archive
* [2022](archive/2022/README.md)
  * [July](archive/2022/july/README.md)
    * [1 Jul - Fri](archive/2022/july/1-jul-fri.md)
```

## Workflow for a new day

1. Duplicate `README.md` into `this-week/{DD}-{mmm}-{day}.md`.
2. Set the page title to the date (e.g., `# 15 Aug - Mon`).
3. Add the entry under `## This week` in `SUMMARY.md`.

## Archiving a week

1. Move files from `this-week/` into `archive/{YYYY}/{month}/`.
2. Create `archive/{YYYY}/README.md` and `archive/{YYYY}/{month}/README.md` if they don't exist (minimal heading only).
3. Update `SUMMARY.md`: remove entries from `## This week`, add them under the appropriate archive section.
