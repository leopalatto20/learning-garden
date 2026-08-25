---
name: ask-garden
description: Answer questions from the garden's notes — use when the user asks to explain, define, compare, or answer anything about course material, topics, or concepts covered in notes/.
---

# Ask Garden

Produce a **grounded** answer written to a Markdown file in `outputs/`: every claim traces to a garden note, and coverage follows tags and links so the answer spans all relevant notes, not just the first hit. Writing to a file (instead of replying inline) is what unlocks rendered Mermaid diagrams, tables and MathJax in Obsidian.

## Steps

1. **Resolve the question to concepts**: name each concept in kebab-case (`bayes-theorem`, `red-black-tree`) — these are candidate filenames and tag values.
2. **Find every relevant note**, not just one:
   - grep `notes/` frontmatter for the concept names among `tags:` values;
   - grep note bodies for the concept names;
   - read the course map in `maps/` covering those notes and pull its other entries on the topic.
3. **Expand along the Links sections** of every note found: each neighbor explains *why* it relates, which decides whether it belongs in the answer (e.g. contrast pairs, foundations). Stop when no new relevant note appears.
4. **Write the answer** to `outputs/<conceptos>.md` — filename in kebab-case Spanish matching the question (`que-es-la-entropia.md`, `diferencia-entre-que-y-como.md`):
   - frontmatter: `question`, plus `created`/`updated`; add `course` when all source notes share one;
   - open with the direct answer, then the supporting detail (headings, tables);
   - attribute structure to the notes' own framing (their warnings, corrections, and simplifications carry into the answer);
   - add a Mermaid diagram whenever the concept benefits from visual structure — flows, contrasts, state machines — even if the source notes have none;
   - link source notes inline as wikilinks where a reader would want to dig deeper (they resolve from anywhere in the vault);
   - anything added from general knowledge goes under `> [!warning] Not from lecture`.
5. **Math gate**: if the answer contains mathematics, apply the **Math / LaTeX** rules in `AGENTS.md` before finishing — `$...$` inline, `$$` on its own lines around display math, never bare LaTeX in prose.
6. **Reply briefly in chat**: a 2–3 sentence summary of the direct answer plus the file path. The full answer lives in the file.

Exception: a quick factual follow-up (one line, no diagram or structure) may be answered directly in chat without creating a file.

Done when: the file exists, every claim in it comes from a found note or sits under a warning callout, and every note found in step 2–3 that bears on the question appears in the answer.
