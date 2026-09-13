# Mathematical Layout Rules

These rules define the layout and typography requirements for translated mathematical PDFs.

They are especially important when Chinese text is overlaid onto an existing mathematical PDF.

---

## 1. General principle

A translated page is not finished merely because:

- the translation is correct;
- the PDF opens successfully;
- text does not technically overlap.

The mathematical page must also look visually coherent.

Mathematical correctness and readable mathematical typography are both required.

---

## 2. Preserve mathematical structure

Never alter mathematical structure merely to improve visual appearance.

Preserve:

- formulas
- variables
- subscripts
- superscripts
- arrows
- arrow direction
- object labels
- morphism labels
- equation order
- composition order
- diagram structure

Layout adjustments must not change mathematical meaning.

---

## 3. Inline mathematics

Inline formulas must visually align with surrounding Chinese text.

Check for:

- formula too high
- formula too low
- Chinese text floating relative to formula
- subscripts causing vertical drift
- superscripts causing vertical drift
- inconsistent baseline between neighboring formulas

Do not rely only on font metrics.

Judge the final rendered result visually.

---

## 4. Parallel formulas on one line

This is a critical requirement.

When two or more mathematical expressions appear on the same line,
they must share a coherent visual baseline.

Example:

`p ∘ s = 1_C    且    k ∘ s' = 1_B`

The following must appear visually aligned:

- left mathematical expression
- Chinese connector
- right mathematical expression

Do not accept:

- one formula visibly higher than the other
- one formula visibly lower than the other
- connector text floating above or below the formulas
- uneven baseline
- visually unbalanced spacing

If automatic placement fails, manually adjust:

- y coordinate
- text-box position
- baseline offset
- formula-box position
- line height
- horizontal spacing

A mathematically correct expression with visibly broken alignment is a layout defect.

---

## 5. Chinese connectors between formulas

Special attention is required when English connectors such as:

- and
- or
- if
- then
- where
- hence
- therefore

are replaced by Chinese text such as:

- 且
- 或
- 如果
- 那么
- 其中
- 因此

Do not simply insert the Chinese connector into the original position
and assume the line remains correctly aligned.

After replacement, recheck:

- baseline
- vertical centering
- spacing before connector
- spacing after connector
- total line balance

---

## 6. Display equations

For standalone equations:

- preserve intended centering;
- preserve indentation where meaningful;
- preserve relationships between consecutive equations;
- maintain consistent vertical spacing;
- preserve the visual grouping of derivations.

Do not let translated prose push related equations into irregular positions.

---

## 7. Multi-line derivations

For derivations spanning multiple lines:

- inspect the whole derivation as one visual unit;
- keep equation spacing consistent;
- preserve equal signs or other structural alignment when present;
- preserve indentation hierarchy;
- do not introduce random horizontal shifts.

Do not treat every line as an unrelated text box.

---

## 8. Subscripts and superscripts

Subscripts and superscripts require visual inspection.

Examples include:

`1_A`

`1_B`

`x_i`

`f^{-1}`

`A^n`

Check that:

- they remain legible;
- they are not clipped;
- they do not collide with surrounding text;
- they do not distort the apparent baseline excessively.

---

## 9. Diagrams

Mathematical diagrams are mathematical content.

Preserve:

- arrow direction
- arrow endpoints
- object positions
- element positions
- morphism labels
- node labels
- relative structure

Do not move a label so far that its mathematical association becomes ambiguous.

If translating a diagram label risks damaging the diagram,
keep the original label instead.

---

## 10. Diagram label placement

Translated diagram labels must remain clearly attached to the correct:

- arrow
- node
- object
- region
- axis
- point

Check that translated labels do not:

- cover arrows
- cover nodes
- overlap formulas
- obscure line intersections
- appear attached to the wrong object

---

## 11. Text boxes

When replacing English text with Chinese:

do not assume the original English bounding box is automatically suitable.

Chinese text may differ in:

- width
- height
- line count
- punctuation spacing
- visual density

Adjust text boxes locally when required.

Avoid:

- overflow
- clipping
- excessive compression
- excessive empty space
- unnatural line breaks

---

## 12. Line wrapping

Line wrapping should preserve natural Chinese reading.

Avoid breaking:

- a mathematical expression in the middle
- a variable from its explanation
- a short mathematical condition across two lines unnecessarily
- punctuation into visually awkward positions

Do not force the original English line breaks when they produce poor Chinese layout.

Preserve paragraph structure rather than exact English line wrapping.

---

## 13. Mathematical text and Chinese punctuation

Check spacing between formulas and Chinese punctuation.

Avoid visually awkward combinations such as:

- formula colliding with comma
- punctuation floating too far from formula
- inconsistent spacing around parentheses
- excessive gaps around inline mathematics

The result should resemble professionally typeset Chinese mathematical prose.

---

## 14. Font consistency

Use the existing validated font configuration whenever possible.

Check:

- Chinese glyph coverage
- Latin glyph compatibility
- mathematical symbol compatibility
- visual weight
- font size consistency

Do not introduce a new font merely to fix one local issue unless necessary.

---

## 15. Searchable text

Whenever the workflow supports it, Chinese text should remain:

- selectable
- searchable
- copyable

Avoid unnecessary rasterization of translated text.

---

## 16. Visual QA

Every translated page must be rendered and visually inspected.

Do not rely solely on:

- text extraction
- PDF coordinates
- script success
- bounding-box collision tests

Human-visible rendering is authoritative for layout QA.

---

## 17. High-risk pages

Inspect these pages more carefully:

- pages with many formulas
- pages with inline formulas mixed with Chinese
- pages with parallel equations
- pages with diagrams
- pages with arrows
- pages with many subscripts or superscripts
- pages with dense text
- pages where translated Chinese is much longer than the English source

Zoom in when necessary.

---

## 18. Local repair

If a layout defect appears:

repair only the affected:

- text block
- formula line
- diagram label
- page

whenever possible.

Do not regenerate the entire translation unit for a local layout problem.

After repair:

1. rerender the page;
2. visually inspect it again;
3. compare against the source if necessary.

---

## 19. Known recurring defect: baseline mismatch

A known recurring defect is:

multiple formulas on the same line appearing at different vertical positions.

This must be actively searched for during QA.

Typical symptom:

`p ∘ s = 1_C`

and

`k ∘ s' = 1_B`

are mathematically correct but visibly misaligned.

This is not acceptable.

Correct the placement until the complete line reads as one coherent mathematical sentence.

---

## 20. Definition of acceptable layout

A page passes layout QA only when:

- formulas are readable;
- inline math aligns naturally with Chinese text;
- parallel formulas share a coherent baseline;
- diagrams remain mathematically correct;
- labels remain attached to the correct structures;
- text does not overlap or clip;
- spacing is visually balanced;
- no obvious layout defect distracts from mathematical reading.
