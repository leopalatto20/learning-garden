# Learning Space

A personal digital garden for my studies. Raw material goes in one end; atomic, densely linked study notes come out the other. The garden grows over time — notes have a maturity, not a final draft.

## Layout

| Path | Purpose |
|---|---|
| `inbox/` | Drop zone for raw class notes, kept exactly as written |
| `slides/` | Professor slide decks, named `<course>-<topic>-<date>` when known |
| `notes/` | The garden: curated atomic notes, one concept per file |
| `maps/` | One index note per course, linking every note it covers |
| `study/` | Generated exam material: flashcards, problem sets |
| `outputs/` | Generated Q&A answers from the ask-garden skill (one file per question) |
| `archive/` | Processed raw notes, moved here after ingestion |

## Note format

- **Atomic**: one concept per note. If a note needs "and" in its title, it is two notes.
- **Filename** is the canonical concept name in kebab-case (`mitosis.md`) — it doubles as the wikilink target.
- **Frontmatter**: `course`, `tags`, `created`, `updated`.
- **Links**: relate notes inline with Obsidian wikilinks (`[[mitosis]]`). Every note carries a short "Links" section explaining *why* each neighbor relates ("builds on", "confuse with X because Y").
- **Math / LaTeX**: in curated Markdown (`notes/`, `maps/`, and `study/`), surround every mathematical expression with MathJax delimiters. Use `$...$` for inline math and `$$` on its own lines around display math:

  ```markdown
  Inline: $x^2 + 1$

  $$
  x^2 + 1 = 0
  $$
  ```

  Put the opening delimiter around the complete expression before writing it and always add the matching closing delimiter. Never leave LaTeX commands or syntax such as `\alpha`, `x^2`, `x_i`, or `\frac{a}{b}` bare in curated prose. Preserve raw `inbox/` files exactly as written, but normalize their math when producing a curated note.
- **Diagrams**: Add Mermaid diagrams automatically when a concept benefits from visual structure — for example, processes, hierarchies, flows, state machines, cycles, or taxonomies. Use them even when the source notes contain no diagram marker.
- **Honesty**: enrich from general knowledge freely, but mark anything uncertain or not covered in class with `> [!warning] Not from lecture` so I know what to verify against my professor's materials.

## Workflows

- New raw notes sitting in `inbox/` → use the **process-notes** skill.
- New deck uploaded to `slides/` → use the **enrich-slides** skill.
- New research source added to `research/` → use the **enrich-research** skill.
- Exam season → use the **exam-prep** skill.
