---
name: process-notes
description: Turn raw study material from inbox/ into atomic, linked garden notes. Use when the user drops new study material in inbox/, or asks to process, clean up, structure, digest, or relate it.
---

# Process Notes

Ingest raw study material from `inbox/` into the garden under `notes/`, following the note format and **Atomization gate** in `AGENTS.md`.

## Math formatting gate

When a curated note contains mathematics, read and apply the **Math / LaTeX** rules in `AGENTS.md` before writing. Surround inline math with `$...$`; surround display math with an opening `$$` and closing `$$` on separate lines. Write both delimiters around the complete expression—never emit bare LaTeX commands or syntax in the curated note. Preserve the raw inbox file and normalize its math only in the curated output.

## Steps

1. **Read every file in `inbox/`** (skip `archive/`). Read fully before writing anything.
2. **Inventory atoms before writing.** For every independently useful concept in the source, record `new note`, `extend existing note`, `overview/link only`, or `fold into existing note`, with a reason. Apply the **Atomization gate** in `AGENTS.md`; an overview or catalog never substitutes for a standalone note when the source supports one.
3. **Split into atoms.** For each inventory entry, decide: new note, addition to an existing note (check `notes/` and `maps/` first), or too minor (fold it into the smallest note that contains it). One concept per note — if a title needs "and", split it.
4. **Rewrite for study use.** Clean structure with headings, definitions up front, worked examples where the raw notes have them. Fix terminology; correct factual errors and say what you corrected. Fill important gaps the professor glossed over, marking them per the honesty rule in AGENTS.md. Add Mermaid diagrams following the diagram rules in AGENTS.md.
5. **Relate.** Link each new note to its neighbors inline and in a "Links" section with the reason for the relation. Hunt across subjects — a concept linking to a neighboring subject is exactly the point of this garden.
6. **Update the course map** in `maps/`: add every new note to the relevant course or subject index under the right topic heading, so the map stays a complete table of contents.
7. **Archive**: move processed raw files into `archive/`.

Done when: `inbox/` holds no unprocessed files, every inventory entry is accounted for, every standalone concept has its own note, no generated note fails the Atomization gate, every new note has frontmatter plus at least one explained link, its map lists it, every concept that benefits from visual structure has an appropriate Mermaid diagram, and any corrections or uncertain enrichments are flagged.
