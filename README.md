# yoga-journey

Study notes and research for yoga certifications and coursework — currently
the M.Sc. Yoga program, alongside earlier YIC and YCB material.

Published at [study.anati.in](https://study.anati.in) via GitHub Pages.

## Layout

- `msc-yoga/` — the published M.Sc. Yoga site, organised the way the program itself is:
  - `semester-1/`, `semester-2/`, ... — one folder per semester
    - `<subject>/` — one folder per subject, named to match the subject
      (e.g. `t3-human-anatomy-physiology`), each with its own `index.html`
      listing that subject's topics
      - `<topic>/notes.html` — the actual notes page, self-contained
      - `<topic>/assets/diagrams/` — diagrams/photos used in that topic's notes
  - `index.html` — programme landing page, lists semesters
- `philosophy/` — yoga philosophy notes, not tied to a specific course
- `practice/` — asanas, sequences, teaching notes, not tied to a specific course
- `assets/shared/` — shared stylesheets/fonts used across topic pages

See `NOTE-FORMAT.md` for the note format used across `msc-yoga/` (and the reasoning behind it).

## What goes here vs. stays external

Raw source material — class-note PDFs, textbook references, question
papers, the full local class-material archive of screenshots and photos —
stays outside the repo, on the local machine, and is only *read from* when
writing a topic's notes. Nothing raw is committed. This repo holds only the
finished, published output: the notes pages themselves (`msc-yoga/`,
`philosophy/`, `practice/`) and the specific diagrams a topic's notes
actually use, copied into that topic's own `assets/diagrams/`.
