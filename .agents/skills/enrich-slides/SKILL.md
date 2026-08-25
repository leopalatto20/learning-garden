---
name: enrich-slides
description: Use a professor's slide deck from slides/ to enrich existing notes. Use when the user uploads or mentions slides, a lecture deck, or professor material to merge into the notes.
---

# Enrich Slides

Use slide decks in `slides/` as ground truth to deepen and correct the garden, following the note format in AGENTS.md. Slides outrank general knowledge: where they disagree with an enriched claim, the slide wins.

## Math formatting gate

When a covered note contains mathematics, read and apply the **Math / LaTeX** rules in `AGENTS.md` before writing. Surround inline math with `$...$`; surround display math with an opening `$$` and closing `$$` on separate lines. Treat slide/source LaTeX as content to normalize, not as Markdown delimiters to omit. Never emit a bare formula or LaTeX command in a curated note.

## Steps

1. **Extract the deck.** For PDFs run `pdftotext` (fall back to other extractors if unavailable); read the extracted text fully before editing anything.
2. **Map coverage.** List which garden notes each deck section touches — including ones it contradicts.
3. **Enrich each covered note**: add missing details, definitions, and exam-relevant specifics; correct errors (state what you corrected); replace vague claims with the source's precise wording. Before enriching or splitting a covered note, apply the **Atomization gate** in `AGENTS.md`; split sibling concepts instead of leaving them as separate primary sections in one note. Add Mermaid diagrams following the diagram rules in AGENTS.md. Cite the source inline like `(slide 12)`.
4. **Seed new notes** for concepts the deck covers that no note has yet, applying the **Atomization gate** in `AGENTS.md` so each independently useful concept gets its own note, linked into its neighbors and course map.
5. **Update the course map** if the deck reveals structure the map lacks.

Done when: every deck section is accounted for in some note (enriched, seeded, or explicitly noted as out of scope), every covered concept that benefits from visual structure has an appropriate Mermaid diagram, corrections are flagged, and maps are current.
