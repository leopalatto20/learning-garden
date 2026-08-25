---
name: process-notes
description: Turn raw class notes from inbox/ into atomic, linked garden notes. Use when the user drops new class notes in inbox/, or asks to process, clean up, structure, digest, or relate their class notes.
---

# Process Notes

Ingest raw class notes from `inbox/` into the garden under `notes/`, following the note format in AGENTS.md.

## Math formatting gate

When a curated note contains mathematics, read and apply the **Math / LaTeX** rules in `AGENTS.md` before writing. Surround inline math with `$...$`; surround display math with an opening `$$` and closing `$$` on separate lines. Write both delimiters around the complete expression—never emit bare LaTeX commands or syntax in the curated note. Preserve the raw inbox file and normalize its math only in the curated output.

## Steps

1. **Read every file in `inbox/`** (skip `archive/`). Read fully before writing anything.
2. **Split into atoms.** For each distinct concept, decide: new note, addition to an existing note (check `notes/` and `maps/` first), or too minor (fold it into the smallest note that contains it). One concept per note — if a title needs "and", split it.
3. **Rewrite for study use.** Clean structure with headings, definitions up front, worked examples where the raw notes have them. Fix terminology; correct factual errors and say what you corrected. Fill important gaps the professor glossed over, marking them per the honesty rule in AGENTS.md. Add Mermaid diagrams following the diagram rules in AGENTS.md.
4. **Relate.** Link each new note to its neighbors inline and in a "Links" section with the reason for the relation. Hunt across courses — a physics concept linking to a mathematics note is exactly the point of this garden.
5. **Update the course map** in `maps/`: add every new note to the course's index note under the right topic heading, so the map stays a complete table of contents.
6. **Archive**: move processed raw files into `archive/`.

Done when: `inbox/` holds no unprocessed files, every new note has frontmatter plus at least one explained link, its course map lists it, every concept that benefits from visual structure has an appropriate Mermaid diagram, and any corrections or uncertain enrichments are flagged.
