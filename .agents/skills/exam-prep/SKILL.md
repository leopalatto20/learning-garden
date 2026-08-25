---
name: exam-prep
description: Generate exam study material from garden notes. Trigger when the user asks to study, revise, memorize, or prepare for an exam.
---

# Exam Prep

Generate material in `study/` for the course, topic, or exam the user names. Ask for scope when none is given.

## Outputs

All files go in `study/<course>-<exam-or-topic>/`:

- **`flashcards.md`** — one card per atomic fact or definition. Prefer recall questions that ask why or how over yes/no questions:
  ```markdown
  Q: Why does quicksort use pivot partitioning instead of merging like mergesort?
  A: ...
  ```
- **`problems.md`** — exam-level calculations, case analyses, failure scenarios, or trace analyses as appropriate. Put the full solution after each problem and link it to source notes, e.g. `See [[quicksort-partitioning]]`.
- **`study-plan.md`** — rank every topic by known exam weight, then by thin or uncertain notes; list its source notes and generated cards/problems.

## Steps

1. **Scope.** Read the course map and every note it covers.
2. **Find weak spots.** Prioritize uncertainty warnings, sparse sections, and missing links in the plan.
3. **Generate.** Create the flashcards, problems, and plan. Add Mermaid where the material benefits from visual structure, and apply the math rules in `AGENTS.md`.
4. **Quiz mode.** When the user asks to drill, quiz interactively from `flashcards.md` instead of regenerating it.

Done when: every in-scope note appears in at least one card or problem; the plan ranks all topics; and every visually useful in-scope concept has an appropriate Mermaid diagram.
