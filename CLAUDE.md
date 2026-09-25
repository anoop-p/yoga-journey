# Working in this repo

This repo holds Anoop's yoga study notes (M.Sc. Yoga, plus earlier YIC/YCB
certifications). Read `README.md` for the folder layout and `NOTE-FORMAT.md`
before touching anything under `anatomy/`.

## Conventions

- **Note format**: topics under `anatomy/` (and eventually `philosophy/`,
  `practice/`) follow the three-layer format in `NOTE-FORMAT.md`
  (Understand / Explain / Connect to practice + a recall strip). Use
  `anatomy/digestive-system/notes.html` as the reference implementation —
  match its structure, CSS classes (`.layer-nav`, `.layer-panel`,
  `.recall-card`, etc.) and JS behavior rather than reinventing it per topic.
- **One HTML file per topic**, self-contained (inline CSS/JS), under
  `<area>/<topic>/notes.html`. Diagrams for that topic live alongside it in
  `<area>/<topic>/assets/diagrams/` and are referenced with a relative path.
- **Raw vs. processed**: small text/PDF class notes are fine to commit under
  `courses/<course>/class-notes/raw-transcripts/` and
  `courses/<course>/question-papers/`. Large audio/video stays external
  (Drive/local) — never commit it here. When in doubt, check `.gitignore`.
- **Question papers are a design input**, not just an archive item — when
  building or revising a topic's note format, check
  `courses/msc/question-papers/` for how that topic is actually examined
  (recall vs. explain vs. synthesis) and shape the three layers accordingly.
- **Source honesty**: when writing the "Connect to practice" layer, if the
  class notes don't state a specific asana/mechanism link, say so in the
  content rather than inventing a plausible-sounding one.

## Before adding a new topic

1. Check `courses/msc/question-papers/` for any past questions on the topic.
2. Check `courses/msc/class-notes/raw-transcripts/` for the relevant class
   notes and reference PDFs.
3. Follow the structure in `anatomy/digestive-system/notes.html` — copy its
   CSS/JS scaffolding rather than rewriting it.
4. If diagrams exist for the topic (photos of textbook figures, etc.), put
   them in `<area>/<topic>/assets/diagrams/` and reference them inline near
   the relevant explanation, not bundled at the end.
