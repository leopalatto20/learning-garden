---
name: enrich-research
description: Use a paper, article, or documentation source in research/ to deepen existing notes. Trigger when the user adds or mentions research material to merge into the garden.
---

# Enrich Research

Integrate sources from `research/` without erasing lecture-grounded claims. A source is authoritative for its own claims; lecture material remains ground truth for exam content. Preserve both sides of a contradiction and flag it for the user.

## Steps

1. **Read the source fully.** Use `pdftotext` for PDFs, read HTML/Markdown directly, and fetch URLs when needed.
2. **Map coverage.** Account for every source section: identify notes it touches, extends, exemplifies, or contradicts.
3. **Enrich covered notes.** Add precise definitions, details, explanations, and worked examples; replace vague claims with the source's wording and state corrections. Cite each addition to an author/year/page or document section. Mark material the source covers but lecture does not with the warning required by `AGENTS.md`. Apply the curated-note format, link, math, and diagram rules in `AGENTS.md`.
4. **Seed missing concepts.** Create atomic notes for uncovered concepts, link them to neighbors, and add them to the course map.
5. **Update the map** when the source reveals missing structure.

Done when: every source section is enriched, seeded, or explicitly out of scope; every lecture contradiction is flagged; every addition has a traceable citation; corrections are stated; and affected maps are current.
