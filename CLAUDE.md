# Working in this repo

This repo holds Anoop's yoga study notes (M.Sc. Yoga, plus earlier YIC/YCB
certifications). Read `README.md` for the folder layout and `NOTE-FORMAT.md`
before touching anything under `msc-yoga/`.

All raw source material (class notes, question papers, textbook references,
photos) lives outside this repo, in Anoop's local class-material archive
(path given by the user — e.g. `.../learning/msc-yoga/`) or the person's
other apps. This repo holds only the finished, published output: nothing
raw gets committed here.

## Conventions

- **Note format**: topics under `msc-yoga/` (and eventually `philosophy/`,
  `practice/`) follow the "detailed handout" spread format in
  `NOTE-FORMAT.md`: no tabs; each section is a diagram + numbered key
  spread, then Understand it / Know this / Memory aid / Common confusion /
  Exam angle / Explain it to someone, optional "Go deeper" folds, and recall
  cards. This replaces the old three-tab format (Understand / Explain /
  Connect to practice). Use
  `msc-yoga/semester-1/t3-human-anatomy-physiology/unit-4-respiratory-system/notes.html`
  as the reference implementation — match its structure, CSS classes
  (`.spread`, `ol.key`, `.blk.und|know|mem|conf|exam|say`, `details.deeper`,
  `.recall-card`, `.src.cls|gen`, `.honest`) and JS behavior rather than
  reinventing it per topic. Topics still in the old tab format (cell,
  tissues, skeletal, muscular, digestive) are rebuilt one at a time, in
  the order Anoop chooses.
- **Folder convention for `msc-yoga/`**: `semester-<n>/<subject-slug>/<topic-slug>/`.
  Subject slugs match the person's own local archive naming exactly
  (`t1-foundations-of-yoga`, `t2-applications-of-hatha-yoga`,
  `t3-human-anatomy-physiology`, `t4-basics-of-sanskrit`,
  `p1-yogic-practices-holistic-health`, `p2-yogic-physiology-lab`) — check
  the local archive (path given by the user) before inventing a new slug.
  Each subject folder has its own `index.html` listing its topics; add a new
  `<a class="topic-card">` entry there (and mark the subject non-"soon" in
  `semester-1/index.html`) whenever a topic's `notes.html` goes in.
- **Unit folders within a subject**: when a subject's syllabus is broken
  into units (as T3 -- Human Anatomy & Physiology I is, per its
  DSCC-18 syllabus), nest topics one level deeper under
  `<subject>/unit-<n>-<unit-slug>/`. A unit with more than one topic gets
  its own `unit-<n>-<unit-slug>/index.html` (same visual pattern as a
  subject index, with a `.soon` card for a unit's topic that has no notes
  yet) and each topic sits in its own `<topic-slug>/notes.html` below that.
  A unit with exactly one topic skips the extra nesting and the topic's
  `notes.html` sits directly at `unit-<n>-<unit-slug>/notes.html` (see
  `t3-human-anatomy-physiology/unit-3-digestive-system/` and
  `unit-4-respiratory-system/`). The subject's own `index.html` links the
  units, not the individual topics. Every topic page's `.back-link` points
  to `../index.html` relative to itself — for a nested topic that resolves
  to the unit index; for a flattened single-topic unit it resolves to the
  subject index, same as before units existed. Moving a topic into (or
  between) unit folders breaks its old URL, since this is a public site;
  leave a tiny redirect stub (`<meta http-equiv="refresh">` to the new
  path) at the old location rather than a dead link — see the stub files
  left at the pre-restructuring paths under `t3-human-anatomy-physiology/`
  for the pattern.
- **One HTML file per topic**, self-contained (inline CSS/JS), at
  `<subject>/<topic>/notes.html`. Diagrams for that topic live alongside it
  in `<subject>/<topic>/assets/diagrams/` and are referenced with a relative
  path (`assets/diagrams/<name>.jpg`), inserted inline near the section they
  illustrate — not bundled at the end. Clean diagrams may instead be drawn
  as inline SVG in the page (no file needed); say so in the page's source
  line.
- **Nothing raw gets committed**: class notes, question papers, textbook
  PDFs, and the full local screenshot/photo archive all stay on the local
  machine and are only read from, never copied into this repo — not even a
  small excerpt. The only files this repo ever gains are a topic's
  `notes.html` and the specific diagrams it uses. When in doubt, check
  `.gitignore`.
- **Question papers are a design input**, not just an archive item — when
  building or revising a topic's note format, check the local archive for
  past question papers on that topic to see how it's actually examined
  (recall vs. explain vs. synthesis) and shape the sections (especially the
  Exam angle blocks and recall cards) accordingly.
- **Source honesty**: in the yoga-connection section (and anywhere else),
  if the class notes don't state a specific asana/mechanism link, say so in
  the content rather than inventing a plausible-sounding one. Tag claims
  that come from outside the class notes as general physiology, and show
  conflicts between sources (class notes vs. textbook) in an `.honest` box
  instead of silently choosing one.
- **Combine all sources into one page**: teacher's notes, Anoop's handwritten
  notes, Yoga & Human Body notes and the reference textbooks go into one
  topic page (no separate teacher/student versions); the question paper
  decides what is core and what goes in a Go-deeper fold.

## Before adding a new topic

1. Ask for (or recall) the local class-material archive path if not already
   known, and check it for question papers and class notes/references on
   the topic.
2. Follow the structure in
   `msc-yoga/semester-1/t3-human-anatomy-physiology/unit-4-respiratory-system/notes.html`
   — copy its CSS/JS scaffolding rather than rewriting it.
3. Pick out only the diagrams/photos actually relevant to that topic, copy
   them into `<subject>/<topic>/assets/diagrams/`, and reference them inline
   near the relevant explanation.
4. Add the topic to its subject's `index.html`, and update
   `semester-1/index.html` if this is the subject's first topic.
