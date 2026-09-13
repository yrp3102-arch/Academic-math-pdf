---
name: academic-math-pdf-translator
description: >
  Translate academic and mathematical PDF content into high-quality
  Simplified Chinese while preserving mathematical notation, diagrams,
  page structure, terminology consistency, and visual quality.
  Use this skill for textbooks, lecture notes, papers, and other
  mathematics-heavy academic PDFs that require faithful translation
  and layout-aware QA.
---

# Academic Math PDF Translator

## Purpose

Use this skill to translate mathematical and academic PDF content into
natural Simplified Chinese while preserving the mathematical meaning,
notation, diagrams, visual structure, and terminology of the source.

This skill is intended for:

- mathematics textbooks
- category theory texts
- physics and mathematical physics texts
- technical lecture notes
- academic papers
- other equation-heavy or diagram-heavy PDFs

This is not a general-purpose literary translation workflow.

The primary objective is:

1. mathematical correctness
2. faithful preservation of structure
3. terminology consistency
4. readable Chinese
5. clean mathematical typography
6. visual fidelity

## Supporting files

Before performing a translation task, read and follow these files when present:

- `references/translation-rules.md`
- `references/math-layout-rules.md`
- `references/qa-checklist.md`

For bounded Session, chapter, section, article, introduction, appendix, or other named-unit translation tasks, also use:

- `templates/session-task.md`

These files extend the rules defined in this `SKILL.md`.

Project-specific files such as:

- `project.md`
- `glossary.json`
- `translation_style.md`
- `progress.json`

take precedence where applicable.

Explicit user instructions take precedence over project defaults and this skill.

# 1. Respect the current project

Before doing any translation, inspect the current project.

Look for existing files such as:

- `glossary.json`
- `translation_style.md`
- `progress.json`
- `project.md`
- existing translated PDFs
- existing QA reports
- existing PDF-processing scripts
- existing fonts and layout logic

If a validated translation pipeline already exists, reuse it.

Do not redesign a working workflow unless there is a concrete failure
that cannot be solved locally.

Project-specific rules override generic recommendations in this skill.

Explicit user instructions override this skill.

---

# 2. Translation unit

Translate only the unit requested by the user.

A unit may be:

- a Session
- a chapter
- a section
- an article
- an introduction
- an appendix
- a specified page range
- a named block between two headings

When the user requests a named section or Session:

1. locate its exact beginning;
2. locate the next structural boundary;
3. translate exactly the requested interval;
4. stop before the next unit unless the user explicitly asks to continue.

Do not skip unnumbered introductory texts merely because they are not
formal chapters or Sessions.

---

# 3. Translation philosophy

Translate mathematical meaning, not isolated words.

The Chinese output should read like a professionally translated
mathematics textbook.

Avoid:

- word-for-word machine translation
- English syntax copied directly into Chinese
- awkward literal phrasing
- unnecessary repetition
- artificial AI explanations
- adding examples that are absent from the source
- simplifying mathematical statements without permission

You may adjust Chinese word order when necessary.

You may split a long English sentence into shorter Chinese sentences
when this improves readability without changing logical structure.

You may merge overly fragmented clauses when this improves naturalness.

Preserve:

- logical strength
- definitions
- conditions
- quantifiers
- implication direction
- distinctions made by the author
- pedagogical rhythm

Do not turn a formal statement into a weaker informal paraphrase.

---

# 4. Terminology

If the project contains `glossary.json`, treat it as authoritative.

Do not silently replace established terminology with alternatives.

When a new mathematical term appears:

1. inspect the complete local context;
2. determine the mathematical meaning;
3. prefer standard Chinese mathematical terminology;
4. check whether a related translation already exists in the project;
5. add the new term to the project glossary if appropriate;
6. report newly introduced terminology.

Do not infer a translation from the English word alone when the term is
context-dependent.

If uncertainty remains, preserve the original English term and flag it
for review rather than guessing.

---

# 5. Preserve mathematics

Translate natural language.

Preserve mathematical content unless translation is explicitly required.

Do not change:

- variable names
- object names
- morphism names
- subscripts
- superscripts
- equations
- inequalities
- arrow directions
- composition order
- brackets
- coordinate order
- labels that function as mathematical symbols

Examples of structures that must remain mathematically identical:

`f : A → B`

`g ∘ f`

`f(x)`

`1_A`

`e ∘ e = e`

Do not replace mathematical notation with prose merely to make the page
look more Chinese.

---

# 6. Mathematical semantic integrity

Mathematical relationships have priority over linguistic elegance.

Always verify:

- domains and codomains
- arrow direction
- order of composition
- identity-object subscripts
- one-sided versus two-sided inverses
- equality versus isomorphism
- assumptions versus conclusions
- object-level versus element-level statements

Never use associativity as if it were commutativity.

Regrouping is allowed where mathematically valid.

Reordering is not.

When the source distinguishes two concepts, the translation must retain
that distinction.

---

# 7. Diagrams are mathematical content

Treat mathematical diagrams as part of the mathematics, not decoration.

Protect:

- nodes
- objects
- arrows
- arrow direction
- arrow labels
- element correspondence
- relative placement when it carries meaning
- commutative structures
- coordinate relationships
- inclusion/retraction structures
- graph structure

Do not move, delete, merge, or reconnect diagram elements merely to make
space for translated text.

Translate diagram labels only when doing so is safe.

If translating a label risks damaging the mathematical structure,
preserve the original label and record it in QA.

A correct English label is preferable to a translated label attached to
the wrong arrow or object.

---

# 8. Preserve page structure

Whenever practical, preserve:

- page size
- page count
- page numbers
- images
- diagrams
- title hierarchy
- paragraph grouping
- mathematical displays
- visual reading order

Do not aggressively redesign the book.

The goal is localization of the existing document, not recreation as a
new textbook.

If the project already uses a validated PDF workflow, reuse it.

For example, if an existing project successfully uses:

- `pypdf`
- `ReportLab`
- original page reuse
- Chinese text overlays

continue using that workflow unless a local technical issue requires a
minimal adjustment.

Do not switch PDF engines merely because another tool exists.

---

# 9. Chinese typography

Chinese mathematical prose must be visually readable.

Check:

- punctuation
- line wrapping
- paragraph spacing
- font size consistency
- Chinese/Latin font compatibility
- spacing around formulas
- text overlap
- clipping
- overflow

Chinese translation is often longer or shorter than English.

Do not simply place translated text into the original box without
checking the visual result.

Adjust layout locally when necessary.

---

# 10. Inline mathematics and baseline alignment

This is a critical project requirement.

Inline formulas must align naturally with surrounding Chinese text.

Do not accept visible vertical drift.

Check especially:

- formulas appearing too high
- formulas appearing too low
- superscripts changing the apparent line baseline
- Chinese text and formulas having mismatched visual centers
- adjacent mathematical blocks sitting at different heights

Parallel expressions on the same line must share a consistent visual
baseline.

For example, an expression structurally equivalent to:

`p ∘ s = 1_C    且    k ∘ s' = 1_B`

must appear visually aligned.

The left formula, Chinese connector, and right formula must form one
coherent line.

Do not accept:

- one formula sitting higher than the other
- uneven vertical positioning
- connector text floating above or below formulas
- excessive or asymmetric spacing

If automatic placement produces visible misalignment, manually adjust:

- y coordinates
- text-box position
- formula-box position
- baseline offsets
- horizontal spacing
- line height

A mathematically correct but visibly misaligned line is not considered
finished.

---

# 11. Display mathematics

For block equations and derivations:

- preserve centering or intended indentation;
- preserve grouping;
- preserve visual hierarchy;
- preserve the relationship between consecutive equations;
- keep related equations at consistent spacing.

Do not let translated prose push equations into visually irregular
positions.

For multi-line derivations, inspect the complete group rather than each
line independently.

---

# 12. Natural Chinese

After translation, reread the Chinese as Chinese.

Check whether definitions, explanations, questions, and transitions
sound natural.

Avoid obvious translationese.

Examples of English instructional phrases should be translated according
to context rather than mechanically:

`Notice that ...`

may become:

- 注意……
- 注意到……
- 请注意……

`It follows that ...`

may become:

- 因此……
- 由此可得……
- 于是……

`Suppose that ...`

may become:

- 设……
- 假设……

Choose according to mathematical context.

Do not force one fixed Chinese expression for every occurrence.

---

# 13. Do not invent content

Do not add:

- explanations
- commentary
- philosophical interpretation
- historical background
- extra proofs
- extra definitions
- examples
- footnotes

unless the user explicitly asks for them.

The translation should represent the source, not the translator.

---

# 14. QA is mandatory

Generating the PDF is not the end of the task.

Every production run must include QA.

QA has four layers:

1. translation QA
2. mathematical QA
3. typography/layout QA
4. visual page QA

Do not skip QA merely because the PDF was generated successfully.

---

# 15. Translation QA

Check for:

- missing translations
- duplicated translations
- incorrect translations
- untranslated body text
- garbled Chinese
- missing glyphs
- square placeholder characters
- obvious typos
- terminology inconsistency
- machine-translation syntax
- unnatural Chinese sentences
- altered pedagogical tone

---

# 16. Mathematical QA

Check:

- formulas
- arrow direction
- composition order
- identity subscripts
- variable names
- object names
- logical conditions
- equality signs
- brackets
- coordinates
- diagram semantics

If the source contains a mathematical relation, compare the translated
page against the original rather than relying on memory.

---

# 17. Layout QA

Specifically inspect:

- inline formula baseline alignment
- parallel equations on the same line
- formula/text vertical alignment
- spacing around Chinese connectors
- equation-group spacing
- diagram-label placement
- overlapping text
- clipped text
- overflow
- broken line wrapping
- inconsistent indentation

A page may be mathematically correct and still fail layout QA.

---

# 18. Visual QA

Render every translated page at high resolution.

Inspect every page visually.

Do not rely only on extracted text or PDF object coordinates.

For complex pages, zoom in substantially.

Pay special attention to:

- formula-heavy pages
- diagrams
- arrows
- labels
- parallel formulas
- text mixed with mathematics
- dense pages
- small subscripts and superscripts

Compare important pages directly with the original source.

---

# 19. Searchability and fonts

When the workflow allows it, translated Chinese text should remain:

- selectable
- searchable
- copyable

Verify that fonts are correctly embedded or otherwise reliably rendered.

Check that the PDF does not contain:

- missing Chinese glyphs
- broken characters
- invisible translated text
- rasterized text where searchable text is expected

---

# 20. Local repair

When QA finds a local problem, repair only the affected area whenever
possible.

Prefer repairing:

- one text block
- one formula line
- one label
- one page

rather than regenerating the entire translation unit.

After repair, rerender and recheck the affected page.

Do not assume a fix succeeded merely because the script completed.

---

# 21. Uncertainty policy

Never guess when a mathematical or textual detail is genuinely unclear.

If necessary:

1. reread the source;
2. inspect surrounding paragraphs;
3. inspect previous and next pages;
4. consult the project glossary;
5. inspect related diagrams.

If uncertainty remains:

- preserve the original content when appropriate;
- flag the issue in QA;
- request human review if necessary.

Correct incompleteness is preferable to confident fabrication.

---

# 22. Project state

If the project uses persistent state files, update them after completing
a unit.

Typical files include:

`glossary.json`

Store terminology decisions.

`translation_style.md`

Store book-specific translation and typography conventions.

`progress.json`

Store completion state, page ranges, output files, newly added terms,
warnings, and unresolved issues.

Do not put project-specific state into this reusable skill.

---

# 23. Output naming

Follow the naming conventions of the current project.

When a source title contains characters that are invalid in filenames,
replace them conservatively.

For example, on Windows:

`:` may be replaced by `-`.

Do not rename previously completed files without a concrete reason.

---

# 24. Completion report

After finishing a translation unit, report at least:

- detected source range
- number of pages processed
- output file
- QA result
- untranslated diagram labels, if any
- unresolved mathematical issues
- layout issues found and repaired
- new terminology
- whether the workflow is ready for the next unit

Do not silently continue into the next section unless requested.

---

# 25. Priority order

When requirements conflict, use this priority:

1. mathematical semantic correctness
2. mathematical diagram correctness
3. formula and notation correctness
4. source fidelity
5. terminology consistency
6. mathematical typography and alignment
7. natural Chinese readability
8. visual polish

However, visible mathematical-layout defects such as broken formula
baselines must still be repaired before the page is considered complete.

---

# 26. Definition of done

A translation unit is complete only when:

- requested content has been translated;
- mathematical meaning is preserved;
- terminology is consistent;
- diagrams remain correct;
- formulas remain correct;
- Chinese reads naturally;
- typography is visually acceptable;
- all pages have undergone visual QA;
- identified local defects have been repaired;
- project state has been updated where applicable;
- the requested boundary has not been exceeded.

Generation alone is not completion.
