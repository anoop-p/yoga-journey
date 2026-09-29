# Working in this repo

This repo holds Anoop's yoga study notes (M.Sc. Yoga, plus earlier YIC/YCB
certifications). Read `README.md` for the folder layout and `NOTE-FORMAT.md`
before touching anything under `msc-yoga/`.

## Conventions

- **Note format**: topics under `msc-yoga/` (and eventually `philosophy/`,
  `practice/`) follow the three-layer format in `NOTE-FORMAT.md`
  (Understand / Explain / Connect to practice + a recall strip). Use
  `msc-yoga/semester-1/t3-human-anatomy-physiology/digestive-system/notes.html`
  as the reference implementation — match its structure, CSS classes
  (`.layer-nav`, `.layer-panel`, `.recall-card`, `.figure-grid`, etc.) and
  JS behavior rather than reinventing it per topic.
- **Folder convention for `msc-yoga/`**: `semester-<n>/<subject-slug>/<topic-slug>/`.
  Subject slugs match the person's own local archive naming exactly
  (`t1-foundations-of-yoga`, `t2-applications-of-hatha-yoga`,
  `t3-human-anatomy-physiology`, `t4-basics-of-sanskrit`,
  `p1-yogic-practices-holistic-health`, `p2-yogic-physiology-lab`) — check
  the local archive (path given by the user) before inventing a new slug.
  Each subject folder has its own `index.html` listing its topics; add a new
  `<a class="topic-card">` entry there (and mark the subject non-"soon" in
  `semester-1/index.html`) whenever a topic's `notes.html` goes in.
- **One HTML file per topic**, self-contained (inline CSS/JS), at
  `<subject>/<topic>/notes.html`. Diagrams for that topic live alongside it
  in `<subject>/<topic>/assets/diagrams/` and are referenced with a relative
  path (`assets/diagrams/<name>.jpg`), inserted inline near the section they
  illustrate — not bundled at the end.
- **Raw vs. processed**: small text/PDF class notes are fine to commit under
  `courses/<course>/class-notes/raw-transcripts/` and
  `courses/<course>/question-papers/`. Large audio/video, and the full local
  class-material archive (screenshots, textbook PDFs), stay external — never
  commit them here. Only the specific diagrams a topic actually uses get
  copied into that topic's `assets/diagrams/`. When in doubt, check `.gitignore`.
- **Question papers are a design input**, not just an archive item — when
  building or revising a topic's note format, check
  `courses/msc/question-papers/` for how that topic is actually examined
  (recall vs. explain vs. synthesis) and shape the three layers accordingly.
- **Source honesty**: when writing the "Connect to practice" layer, if the
  class notes don't state a specific asana/mechanism link, say so in the
  content rather than inventing a plausible-sounding one.

## Before adding a new topic

1. Check `courses/msc/question-papers/` for any past questions on the topic.
2. Check the local class-material archive (screenshots, notes, references)
   for the relevant subject/topic, and `courses/msc/class-notes/raw-transcripts/`
   for anything already committed.
3. Follow the structure in
   `msc-yoga/semester-1/t3-human-anatomy-physiology/digestive-system/notes.html`
   — copy its CSS/JS scaffolding rather than rewriting it.
4. Pick out only the diagrams/photos actually relevant to that topic, copy
   them into `<subject>/<topic>/assets/diagrams/`, and reference them inline
   near the relevant explanation.
5. Add the topic to its subject's `index.html`, and update
   `semester-1/index.html` if this is the subject's first topic.
