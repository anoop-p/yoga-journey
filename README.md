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
- `courses/`
  - `msc/` — small raw source material for the M.Sc. program (see below)
    - `class-notes/raw-transcripts/` — raw class notes and reference PDFs as given
    - `question-papers/` — old question papers, used to calibrate note depth/format
  - `yic/`, `ycb/` — earlier certifications (to be populated)
- `assets/shared/` — shared stylesheets/fonts used across topic pages

See `NOTE-FORMAT.md` for the note format used across `msc-yoga/` (and the reasoning behind it).

## What goes here vs. stays external

Large raw material — audio/video recordings, big scanned PDFs, the full
local class-material archive — stays outside the repo and is *referenced*,
not committed. Small text-based raw material (class notes, question papers,
short reference PDFs) is fine to commit directly, as in `courses/msc/`.
Processed, finished notes (`msc-yoga/`, `philosophy/`, `practice/`) are
what this repo is really for — along with the specific diagrams a topic's
notes actually use, copied into that topic's own `assets/diagrams/`.
