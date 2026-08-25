---
name: enrich-research
description: Use a paper, article, or documentation page from research/ to enrich existing notes. Use when the user drops a paper into research/, or mentions reading material, papers, articles, or docs to merge into the notes.
---

# Enrich Research

Use sources in `research/` to deepen the garden, following the note format in AGENTS.md. Research sources are authoritative for their own claims, but lecture material stays ground truth for exam content: when a source contradicts a lecture-derived claim, do not silently overwrite it — add the source's version alongside and flag the discrepancy so the user can judge.

## Math formatting gate

When a covered note contains mathematics, read and apply the **Math / LaTeX** rules in `AGENTS.md` before writing. Surround inline math with `$...$`; surround display math with an opening `$$` and closing `$$` on separate lines. Treat source LaTeX as content to normalize, not as Markdown delimiters to omit. Never emit a bare formula or LaTeX command in a curated note.

## Steps

1. **Extract the source.** For PDFs run `pdftotext` (fall back to other extractors if unavailable); read HTML/markdown files directly; fetch URLs if the source is a link. Read fully before editing anything.
2. **Map coverage.** List which garden notes each source section touches — including ones it contradicts, extends, or gives better examples than.
3. **Enrich each covered note**: add missing details, definitions, deeper explanations, and worked examples; replace vague claims with the source's precise wording. Cite inline like `(Author, Year, p. 12)` or `(Docs > <section>)`, so any addition traces back to the exact spot in the source. Anything the source covers that lecture does not keeps its `> [!warning] Not from lecture` status per AGENTS.md.
4. **Seed new notes** for concepts the source covers that no note has yet, linked into their neighbors and course map.
5. **Update the course map** if the source reveals structure the map lacks.

Done when: every source section is accounted for in some note (enriched, seeded, or explicitly noted as out of scope), every contradiction with lecture material is flagged rather than silently resolved, additions carry traceable citations, corrections are stated, and maps are current.
