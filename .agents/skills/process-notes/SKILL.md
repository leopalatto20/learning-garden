---
name: process-notes
description: Turn raw class notes from inbox/ into atomic, linked garden notes. Use when the user drops new class notes in inbox/, or asks to process, clean up, structure, digest, or relate their class notes.
---

# Process Notes

Ingest raw class notes from `inbox/` into the garden under `notes/`, following the note format in AGENTS.md.

## Math formatting gate

When a curated note contains mathematics, read and apply the **Math / LaTeX** rules in `AGENTS.md` before writing. Surround inline math with `$...$`; surround display math with an opening `$$` and closing `$$` on separate lines. Write both delimiters around the complete expression—never emit bare LaTeX commands or syntax in the curated note. Preserve the raw inbox file and normalize its math only in the curated output.

## Steps

1. **Scope.** `inbox/` holds one subdirectory per subject (`inbox/<subject>/`); loose files at the inbox root are unsorted — ask which subject they belong to before processing them. If the user names a subject, process only `inbox/<subject>/`. With no subject named, process every subject that has files. The subdirectory name is the subject's canonical name: use it for the `course` frontmatter value and the map filename in `maps/`.
2. **Read every file in scope** fully before writing anything.
3. **Split into atoms.** For each distinct concept, decide: new note, addition to an existing note (check `notes/` and `maps/` first), or too minor (fold it into the smallest note that contains it). One concept per note — if a title needs "and", split it.
4. **Rewrite for study use.** Clean structure with headings, definitions up front, worked examples where the raw notes have them. Fix terminology; correct factual errors and say what you corrected. Fill important gaps the professor glossed over, marking them per the honesty rule in AGENTS.md. Add Mermaid diagrams automatically whenever a concept benefits from visual structure — for example, algorithms and pipelines, state machines, taxonomies, proofs, flows, timelines, or message sequences — even when the raw notes contain no diagram marker.
5. **Relate.** Link each new note to its neighbors inline and in a "Links" section with the reason for the relation. Hunt across courses — an economics concept linking to a statistics note is exactly the point of this garden.
6. **Update the course map** in `maps/`: add every new note to the course's index note under the right topic heading, so the map stays a complete table of contents.
7. **Archive**: move processed raw files into `archive/<subject>/`, preserving the subject subdirectory.

Done when: every file in scope is processed (`inbox/<subject>/` emptied, root files sorted or left untouched if unresolved), every new note has frontmatter plus at least one explained link, its course map lists it, every concept that benefits from visual structure has an appropriate Mermaid diagram, and any corrections or uncertain enrichments are flagged.
