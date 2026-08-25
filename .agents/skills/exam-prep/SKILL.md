---
name: exam-prep
description: Generate exam study material from the garden — flashcards, practice problems, and a prioritized study plan. Use when exam season is mentioned or the user asks to study, revise, memorize, or prepare for a test.
---

# Exam Prep

Produce study material in `study/` from garden notes, scoped to a course, topic, or upcoming exam the user names. When nothing is named, ask.

## Math formatting gate

When flashcards, problems, or plans contain mathematics, read and apply the **Math / LaTeX** rules in `AGENTS.md` before writing. Surround inline math with `$...$`; surround display math with an opening `$$` and closing `$$` on separate lines. Put both delimiters around the complete expression before writing it; never emit bare LaTeX commands or syntax in the generated Markdown.

## Outputs

All files go in `study/<course>-<exam-or-topic>/`:

- **flashcards.md** — one card per atomic fact or definition, phrased so recall requires thinking (why/how over yes/no). Format:

  ```markdown
  Q: Why does quicksort use pivot partitioning instead of merging like mergesort?
  A: ...
  ```

- **problems.md** — worked example problems at exam difficulty: calculations, case analysis, "explain what happens when X breaks", trace analysis as fits the subject. Full solution after each problem, with links back to the source notes (`See [[quicksort-partitioning]]`).
- **study-plan.md** — topics ranked by weight (from maps and any syllabus known) and by how thin their notes look; each topic lists its notes and its cards/problems.

## Steps

1. **Scope**: read the course map and every note it covers.
2. **Find weak spots**: notes marked with uncertainty warnings, sparse sections, and missing links are the priorities — surface them in the plan.
3. **Generate** flashcards, problems, and plan. Add Mermaid diagrams automatically in the relevant study material whenever a concept benefits from visual structure — for example, algorithms and pipelines, state machines, taxonomies, proofs, flows, timelines, or message sequences — without waiting for a source-note or user marker.
4. **Quiz mode**: if the user asks to drill, quiz interactively from `flashcards.md` instead of regenerating material.

Done when: every note in scope is represented by at least one card or problem, the plan ranks all topics, and each in-scope concept that benefits from visual structure has an appropriate Mermaid diagram.
