---
name: process-notes
description: Turn raw class notes from inbox/ into atomic, linked garden notes. Trigger when the user adds, cleans up, structures, digests, or relates class notes.
---

# Process Notes

Ingest raw notes from `inbox/` into `notes/`; preserve the raw files and follow the curated-note contract in `AGENTS.md`.

## Steps

1. **Scope.** A named subject limits work to `inbox/<subject>/`. Without one, process every subject directory containing files. Use each directory name as the `course` frontmatter value and map filename. Root-level inbox files are unsorted; ask for their subject before processing them.
2. **Read fully.** Read every file in scope before writing.
3. **Split into atoms.** Check `notes/` and `maps/` first. For each concept, choose a new note, add it to an existing note, or fold it into the smallest suitable note; split titles that need “and”.
4. **Rewrite for study.** Put definitions first, preserve useful examples, fix terminology and factual errors, and state corrections. Fill important gaps with the warning required by `AGENTS.md`. Add Mermaid diagrams when visual structure helps, and normalize math only in curated output.
5. **Relate.** Link each new or changed note to relevant neighbors, including across courses, and explain each relation in its `Links` section.
6. **Update the course map.** Add every new note under the appropriate topic heading.
7. **Archive.** After successful processing, move raw files to `archive/<subject>/`, preserving the subject directory.

Done when: every in-scope file is processed; subject directories are empty; unresolved root files remain untouched; every new note has valid frontmatter, an explained link, and a course-map entry; useful diagrams are present; and corrections or uncertain enrichments are flagged.
