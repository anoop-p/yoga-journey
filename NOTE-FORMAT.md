# Note format for anatomy/physiology topics

Decided 2026-09-25, based on `msc-yoga/semester-1/t3-human-anatomy-physiology/digestive-system/notes.html` as the
reference implementation. Read that file's Stomach section first if you
want a concrete example before changing this format.

## Why this format

Reformatting class notes with headers and color didn't help understanding —
it just made the same facts easier to *find*, not easier to *get*. Two
things fixed that:

1. **Understanding has to come before exam-ready facts, not instead of them.**
   Anoop needs both: real comprehension, and the ability to reproduce
   Def/Stru/Fun-style answers on paper.
2. **The M.Sc. question paper itself rewards graduated understanding**, not
   just recall. See `courses/msc/question-papers/msc_first_semester_question_paper.pdf`
   (Semester 1, Human Anatomy and Physiology, DSCC-18):

   | Section | Marks | Style | Example |
   |---|---|---|---|
   | A (10 of 13) | 2 marks each | Recall | "What is a cell?", "Name one organelle" |
   | B (4 of 6) | 5 marks each | Mechanism / explain | "What causes muscle fatigue?", "Draw and label the Respiratory System" |
   | C (2 of 3) | 10 marks each | Synthesis — physiology tied to yoga practice | "How do asanas help in digestion?" |

## The format: three layers + a recall strip, per organ/topic

Each topic section has three tabs:

1. **Understand** — plain-language narrative with at least one real analogy
   or mechanism explanation ("why", not just "what"). This is what makes
   Layers 2 and 3 answerable at all — it's not exam-shaped, and that's
   intentional.
2. **Explain** (Section B style, ~5 marks) — Def/Stru/Fun structured answer,
   tables/diagrams as needed. This is close to how your class notes are
   already written.
3. **Connect to practice** (Section C style, ~10 marks) — the physiological
   *why* behind a named asana/pranayama, not just "pose X helps". Where the
   class notes don't state a specific link, say so plainly rather than
   inventing one.

Below the tabs: a **quick-recall strip** of flip cards (Section A style,
2 marks) — short facts pulled from the content above, not written
separately. If Layer 1 is genuinely understood, most of these should be
answerable without memorizing them as a separate list.

## Open questions / things to revisit

- Whether the quick-recall strip should be auto-generated from the other
  layers instead of hand-written per topic.
- Whether the "Connect to practice" content (asana links + physiological
  reasoning) should be cross-checked against a real yoga-physiology
  reference — right now that reasoning is Claude's synthesis, not
  something confirmed by a textbook or teacher.
- A separate `Disorders & Yoga` consolidated section currently exists
  alongside the per-organ "Connect to practice" content, for cram-before-
  exam use. Consider whether to keep both or merge.

## Implementation notes

- Single self-contained HTML file per topic, no external framework — see
  `msc-yoga/semester-1/t3-human-anatomy-physiology/digestive-system/notes.html`.
- Tabs and recall-card flip are implemented generically in a shared
  `<script>` block: any section with a `.layer-nav` + three `.layer-panel`
  elements (`data-panel="understand|explain|practice"`) gets working tabs
  automatically. No per-section JS needed when adding a new topic.
- Diagrams: place image files under `<topic>/assets/diagrams/` and
  reference them with a relative path from the topic's HTML file, so
  image and text stay together and travel with the topic if it moves.
