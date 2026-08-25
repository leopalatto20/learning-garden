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
  Q: What distinguishes a hypothesis from a theory?
  A: ...
  ```

- **problems.md** — worked example problems at exam difficulty: calculations, scenarios, "explain what happens when X breaks", trace analysis as fits the subject. Full solution after each problem, with links back to the source notes (`See [[hypothesis]]`).
- **study-plan.md** — topics ranked by weight (from maps and any syllabus known) and by how thin their notes look; each topic lists its notes and its cards/problems.

## Steps

1. **Scope**: read the course map and every note it covers.
2. **Find weak spots**: notes marked with uncertainty warnings, sparse sections, and missing links are the priorities — surface them in the plan.
3. **Generate** flashcards, problems, and plan. Add Mermaid diagrams following the diagram rules in AGENTS.md.
4. **Quiz mode**: if the user asks to drill, quiz interactively from `flashcards.md` instead of regenerating material.

Done when: every note in scope is represented by at least one card or problem, the plan ranks all topics, and each in-scope concept that benefits from visual structure has an appropriate Mermaid diagram.
