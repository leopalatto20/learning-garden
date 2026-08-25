# Learning Space

My digital garden for my cybersecurity degree. I dump raw material in; atomic, linked study notes come out.

Want to make your own? See the [setup guide](SETUP.md).

## How to use it

Everything runs through chat with my coding agent. There are three moves:

### 1. Process class notes

1. Drop raw notes into `inbox/` — Obsidian exports, messy markdown, whatever. Don't clean them up.
2. Say: *"process my notes"*.
3. The agent splits them into atomic notes in `notes/` (one concept per file), fixes errors, fills gaps, adds Mermaid diagrams automatically when a concept benefits from visual structure, cross-links everything, and updates the course index in `maps/`. Raw originals move to `archive/`.

Run this after every class (or batch a week at once). Small batches link better.

### 2. Enrich with professor slides

1. Drop the deck into `slides/`.
2. Say: *"enrich with the <topic> slides"*.

Slides count as ground truth — where they contradict an enriched claim, they win. Additions cite `(slide N)` so I can trace anything back to lecture.

### 3. Exam prep

When exams approach, say: *"prep me for the <course> exam"*. That generates, in `study/<course>/`:

- **flashcards.md** — Q/A cards to memorize
- **problems.md** — worked practice problems at exam difficulty
- **study-plan.md** — topics ranked by weight and by how thin the notes look

To drill instead of reading: *"quiz me on <course>"*.

## Where things live

| Path | Purpose |
|---|---|
| `inbox/` | Raw class notes, drop zone |
| `slides/` | Professor slide decks |
| `notes/` | The garden — one concept per file, kebab-case names |
| `maps/` | One index note per course |
| `study/` | Generated flashcards, problems, plans |
| `archive/` | Processed raw notes |

## Conventions that matter

- Notes link with `[[wikilinks]]`, so they open fine in Obsidian too.
- Curated Markdown uses MathJax: surround inline expressions with `$...$` and put display expressions between `$$` delimiters on their own lines. For example, write `$x^2$` — never bare `x^2` or `\alpha` in prose.
- Anything the agent enriched from general knowledge carries a `> [!warning] Not from lecture` callout — verify those against course material before trusting them on an exam.
- The garden is never done: notes can always be split further, linked further, corrected later.
