---
name: enrich-research
description: Use research sources in research/ to deepen existing garden notes. Trigger when the user adds, mentions, or asks to merge research material into the notes.
---

# Enrich Research

Use material in `research/` to deepen and correct the garden while preserving lecture authority. Research can explain, extend, or challenge a note; it does not replace lecture-grounded claims for exam purposes.

## Math and note-format gate

Before editing a curated note, apply the note-format, MathJax, linking, and Mermaid rules in `AGENTS.md`. Mark research additions that were not covered in lecture with `> [!warning] Not from lecture`. Cite every research-derived addition to its source file and the relevant page, section, or heading.

## Steps

1. **Read the sources fully.** Read Markdown directly. For PDFs, extract text with `pdftotext` and inspect the complete extraction; use an appropriate extractor if unavailable. Keep each source's title and citation details.
2. **Map coverage.** For every source section, identify garden notes it supports, extends, exemplifies, or contradicts. Include relevant course maps and neighboring notes before deciding scope.
3. **Enrich covered notes.** Add precise definitions, explanations, details, and examples. Cite each addition. Apply the **Atomization gate** in `AGENTS.md`; split sibling concepts rather than leaving them as separate primary sections in one note. Preserve the source-material version when research conflicts with it, record the conflict explicitly, and state any correction rather than silently replacing the claim.
4. **Seed missing concepts.** Apply the **Atomization gate** in `AGENTS.md` and create a separate note for each independently useful concept covered by the research but absent from the garden. Add frontmatter, links explaining each relationship, required warnings, and the notes to the appropriate course map.
5. **Update affected maps.** Add missing structure and links revealed by the research; keep unrelated maps unchanged.
6. **Audit the result.** Check that every source section is enriched, represented by a new note, or explicitly out of scope; every research addition is traceable; every source-material contradiction is visible; the Atomization gate is satisfied; required warnings and math delimiters are present; and affected maps link to all created or changed notes.

Done when: all source sections are accounted for, covered notes and missing concepts are handled, every addition has a source citation and non-lecture warning where required, contradictions and corrections are explicit, and affected course maps are current.
