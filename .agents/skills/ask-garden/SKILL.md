---
name: ask-garden
description: Answer questions from garden notes. Trigger for explanations, definitions, comparisons, or other questions about concepts covered in notes/.
---

# Ask Garden

Write a grounded Markdown answer to `outputs/`. Every claim must come from a relevant garden note or be marked as general knowledge; search the whole relevant note neighborhood, not just the first match.

## Steps

1. **Resolve concepts.** Translate the question into candidate kebab-case filenames and tag values.
2. **Find coverage.** Search note frontmatter and bodies for every concept. Read the relevant course maps and add other entries on the same topic.
3. **Expand context.** Follow the `Links` sections of every candidate note; keep neighbors whose stated relation bears on the question. Stop when no relevant note remains.
4. **Write the answer** to `outputs/<conceptos>.md` using a Spanish kebab-case filename matching the question. Include `question`, `created`, and `updated` frontmatter, plus `course` when shared by all source notes. Lead with the direct answer, then supporting detail. Preserve notes' warnings, corrections, and framing; link source notes inline; add Mermaid where visual structure helps; mark general-knowledge additions with `> [!warning] Not from lecture`.
5. **Apply the math rules** in `AGENTS.md` before finishing.
6. **Reply briefly** in chat with the direct answer and output path.

A one-line factual follow-up may be answered directly without creating a file.

Done when: the output file exists; every claim is grounded or warned; and every relevant note found in steps 2–3 appears in the answer.
