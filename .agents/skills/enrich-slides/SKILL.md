---
name: enrich-slides
description: Use a professor's slide deck in slides/ to deepen existing notes. Trigger when the user adds or mentions slides or other lecture material to merge into the garden.
---

# Enrich Slides

Treat slide decks in `slides/` as lecture ground truth. They outrank general knowledge and previously enriched claims when the two disagree.

## Steps

1. **Read the deck fully.** Extract PDF text with `pdftotext` and use another extractor if necessary.
2. **Map coverage.** Account for every deck section and identify the notes it touches, including contradictions.
3. **Enrich covered notes.** Add definitions, explanations, exam-relevant specifics, and worked examples; replace vague claims with the lecture's wording, then state corrections. Cite additions as `(slide N)`. Add Mermaid diagrams where the concept benefits from visual structure. Apply the curated-note format, math, link, and honesty rules in `AGENTS.md`.
4. **Seed missing concepts.** Create atomic notes, link them to neighbors, and add them to the course map.
5. **Update the map** when the deck reveals missing structure.

Done when: every deck section is enriched, seeded, or explicitly out of scope; corrections are flagged; every visually useful covered concept has an appropriate Mermaid diagram; and affected maps are current.
