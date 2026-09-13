# Session Translation Task Template

Use this template when translating one Session, chapter, section, article, or other bounded unit from an academic or mathematical PDF.

This template must be used together with:

- `SKILL.md`
- `references/translation-rules.md`
- `references/math-layout-rules.md`
- `references/qa-checklist.md`

Project-specific files such as the following must also be read when present:

- `project.md`
- `glossary.json`
- `translation_style.md`
- `progress.json`

---

# 1. Requested unit

Translate only the following requested unit:

**Unit title:**  
`{{UNIT_TITLE}}`

**Optional Chinese title:**  
`{{CHINESE_TITLE}}`

**Unit type:**  
`{{UNIT_TYPE}}`

Examples:

- Session
- Chapter
- Section
- Article
- Introduction
- Appendix
- Unnumbered text

---

# 2. Boundary detection

Locate the exact beginning of:

`{{UNIT_TITLE}}`

Then locate the next structural boundary:

`{{NEXT_UNIT_TITLE}}`

Translate everything belonging to the requested unit.

Stop before the next unit begins.

Do not automatically continue into the next Session, chapter, or section.

If the boundary is uncertain:

inspect:

- table of contents
- heading hierarchy
- surrounding pages
- typography
- previous and next structural units

Record any unresolved boundary uncertainty in QA.

---

# 3. Project continuity

Before translating:

1. read `glossary.json` if present;
2. read `translation_style.md` if present;
3. read `progress.json` if present;
4. inspect previous translated units when useful;
5. inspect existing PDF generation scripts and workflow.

Reuse the validated project workflow.

Do not redesign a working translation pipeline unless necessary.

---

# 4. Translation

Translate all natural-language content belonging to the requested unit.

This includes, when applicable:

- headings
- body text
- explanatory text
- captions
- footnotes
- natural-language diagram labels
- unnumbered introductory text

Do not translate mathematical variables or notation.

Follow:

`references/translation-rules.md`

---

# 5. Mathematical preservation

Preserve exactly:

- formulas
- variables
- object names
- map names
- arrows
- arrow directions
- subscripts
- superscripts
- composition order
- brackets
- coordinate order
- diagram relationships

If any mathematical expression is unclear, compare directly with the source.

Do not reconstruct formulas from memory.

---

# 6. Session-specific mathematical risks

Before translation, identify the concepts in this unit that are especially vulnerable to mistranslation.

Record them here:

`{{SESSION_SPECIFIC_MATH_RISKS}}`

Examples:

- composition order
- domain versus codomain
- one-sided inverse
- isomorphism versus equality
- section versus retraction
- idempotent versus identity
- object versus coordinate representation
- element-level versus morphism-level description
- universal property direction

Use these risks as additional QA targets.

---

# 7. Terminology

Use the existing project glossary.

Do not silently change established translations.

If new important terms appear:

1. inspect full context;
2. select a standard mathematical Chinese translation;
3. add it to `glossary.json` when appropriate;
4. list it in the completion report.

If uncertain, flag the term instead of guessing.

---

# 8. PDF production

Reuse the project's validated PDF production method.

If the current project uses:

- original PDF pages
- `pypdf`
- `ReportLab`
- Chinese text overlays

continue using that workflow.

Preserve:

- page size
- page count where appropriate
- images
- diagrams
- formulas
- page numbers
- original visual structure

Do not change PDF engines without a concrete reason.

---

# 9. Mathematical layout

Follow:

`references/math-layout-rules.md`

Pay special attention to:

- inline math baselines
- parallel formulas
- Chinese connectors between formulas
- subscripts and superscripts
- diagram labels
- dense mathematical pages
- text overflow

A mathematically correct but visibly misaligned formula line is not finished.

---

# 10. Known baseline defect

Actively inspect for the recurring defect where two same-line mathematical expressions sit at different vertical positions.

For expressions structurally similar to:

`p ∘ s = 1_C    且    k ∘ s' = 1_B`

verify:

- one coherent baseline
- aligned formulas
- vertically balanced Chinese connector
- balanced spacing

Repair local placement if necessary.

---

# 11. QA

After PDF generation, perform the full QA workflow defined in:

`references/qa-checklist.md`

QA is mandatory.

At minimum verify:

- translation completeness
- Chinese readability
- terminology consistency
- mathematical correctness
- formula preservation
- diagram correctness
- baseline alignment
- text overlap
- clipping
- font rendering
- searchability
- full-page visual quality

---

# 12. Visual inspection

Render every page in the requested unit to high-resolution images.

Inspect all pages.

For high-risk pages, zoom in significantly.

Compare complex mathematical pages directly with the source PDF.

Do not accept the output merely because the script completed successfully.

---

# 13. Repair policy

If QA finds a local defect:

repair only the affected:

- text block
- formula
- label
- diagram area
- page

whenever possible.

After repair:

1. rerender;
2. reinspect;
3. verify the original defect is gone;
4. verify the repair introduced no new defect.

Avoid rerunning the entire unit unnecessarily.

---

# 14. Uncertainty

Do not guess.

If something is unclear:

1. inspect the source;
2. inspect surrounding paragraphs;
3. inspect adjacent pages;
4. inspect glossary and previous units;
5. inspect diagrams.

If uncertainty remains:

- preserve source content where appropriate;
- flag the issue;
- record it in QA.

---

# 15. Output files

Use the project naming convention.

Suggested PDF output:

`{{OUTPUT_PDF}}`

Suggested QA report:

`{{OUTPUT_QA}}`

If the project uses persistent state, update:

- `glossary.json`
- `translation_style.md`
- `progress.json`

---

# 16. Progress update

When the unit is completed, record:

- unit title
- status
- source page range
- processed page count
- output PDF
- QA report
- new terminology
- preserved English labels
- repaired layout issues
- unresolved issues
- human-review items

Do not mark the unit complete if major QA issues remain.

---

# 17. Completion report

Report:

1. detected source page range;
2. number of pages processed;
3. output PDF path;
4. QA report path;
5. whether translation is complete;
6. whether any English labels were intentionally retained;
7. mathematical issues found;
8. layout issues found;
9. baseline-alignment issues found and repaired;
10. new terminology added;
11. unresolved items;
12. whether the workflow is ready for the next unit.

---

# 18. Stop condition

After completing the requested unit:

STOP.

Do not automatically begin:

`{{NEXT_UNIT_TITLE}}`

unless the user explicitly requests it.