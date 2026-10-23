# Note format for anatomy/physiology topics

Revised 2026-10-23 ("detailed handout" spreads). Reference implementation:
`msc-yoga/semester-1/t3-human-anatomy-physiology/unit-4-respiratory-system/notes.html`.
The earlier three-tab format (Understand / Explain / Connect to practice, decided
2026-09-25) is **replaced**; topics still in that format (cell, tissues, skeletal,
muscular, digestive) get rebuilt one at a time, in an order Anoop decides.

## Why this format

Anoop found the handout-style notes (diagram and explanation side by side, with
real depth) clearer than tabs: seeing the picture and the words together is
what made the concept click. Tabs hid content behind clicks and split a
diagram from the explanation of it. The same page also has to let him
**explain the topic to other people** (the course teacher wants him able to
teach it), so each topic ends with a short spoken version.

The M.Sc. question paper (Semester 1, DSCC-18) still shapes what goes in:

| Section | Marks | Style | Example |
|---|---|---|---|
| A (10 of 13) | 2 marks each | Recall | "Name the fluid in the lungs' cavity" |
| B (4 of 6) | 5 marks each | Mechanism / explain | "How do we breathe?", "Draw and label the Respiratory System" |
| C (2 of 3) | 10 marks each | Synthesis, physiology tied to yoga practice | "How does breathing affect the body in yoga practice?" |

## The format: continuous spreads, no tabs

Each topic page is a set of numbered sections (sidebar nav scrolls to them;
nothing is hidden behind tabs). Each section is built from these parts, in
this order. Leave a part out only when it has nothing honest to say.

1. **Spread**: a diagram and a numbered key side by side (`.spread` + `ol.key`
   with `.fig`); stacked on phones. Numbers in the drawing match the key.
   Use Anoop's own notebook drawing when it is clear; draw a clean inline SVG
   (theme colours via the CSS variables, numbered `.bd` badges) where there is
   no good drawing or his is too faint.
2. **Understand it** (`.blk.und`): plain-language "why", with a real analogy
   or mechanism. This is what makes everything below answerable.
3. **Know this** (`.blk.know`): the extra depth and the exact facts and values
   from the class notes, as bullets or a table.
4. **Memory aid** (`.blk.mem`): a mnemonic or one-line rule. Label made-up
   mnemonics as made up.
5. **Common confusion** (`.blk.conf`): the pairs students mix up.
6. **Exam angle** (`.blk.exam`): which question in the paper, how many marks,
   and how to structure the answer. For "draw and label" questions include a
   drawing checklist (`ul.chk`).
7. **Explain it to someone** (`.blk.say`): a 30-second spoken version.
8. **Go deeper** (`details.deeper`): optional, untested extras (disorders,
   surfactant, Bohr effect...). Folded by default; opened automatically for print.
9. **Recall cards**: flip cards (`.recall-strip` / `.recall-card`) for Section-A
   style questions, written from the content above.

The final section of a topic is the **yoga connection** (the 10-mark answer):
a table of points to write, each tagged with where it comes from.

## Source honesty (applies to every part)

- Tag claims that go beyond the class notes: `.src.cls` for "from the class
  notes" and `.src.gen` for "general physiology, not in the class notes".
- Where the class notes disagree with a textbook or with each other, show it in
  a `.honest` box and say which figure the page uses. Do not silently pick one.
- Never invent an asana, pranayama or mechanism link. If the class notes only
  say "may influence" or "depends on technique", write it that way.
- Diagrams drawn by Claude say so in the page's source line.

## Sources to combine

Teacher's typed notes, Anoop's handwritten class notes (and their diagrams),
the Yoga & Human Body notes, and the textbooks in `references/`
(Ross & Wilson, NCERT), with the question paper deciding what is core and what
goes in a Go-deeper fold. Raw sources are read from Anoop's local archive and
are never committed (see CLAUDE.md).

## Implementation notes

- Single self-contained HTML file per topic (inline CSS/JS), same shell as
  the other topic pages: sidebar, search box, mobile bar, light/dark themes.
- Nav buttons scroll to `#sec-<id>`; an IntersectionObserver highlights the
  current section. Recall cards flip on click. Print CSS hides the sidebar,
  opens the Go-deeper folds and shows card answers.
- Diagrams that are image files go under `<topic>/assets/diagrams/` and are
  referenced with a relative path. Inline SVGs need no files.
- Non-ASCII characters are written as HTML entities (`&#8322;`), so the file
  stays ASCII-clean.

## Open questions

- Which topic is rebuilt next (cell, tissues, skeletal, muscular, digestive).
- Whether the Disorders & Yoga consolidated section should be merged into the
  per-topic Go-deeper folds.
