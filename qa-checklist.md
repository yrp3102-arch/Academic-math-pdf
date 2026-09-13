# Translation and PDF QA Checklist

This checklist defines the mandatory quality assurance process for
academic and mathematical PDF translation.

A translation is not complete until all relevant QA stages have passed.

---

## 1. QA principle

PDF generation is not completion.

Every translated unit must be checked for:

- translation quality
- mathematical correctness
- terminology consistency
- mathematical typography
- diagrams and arrows
- page layout
- font rendering
- visual quality
- output completeness

If a defect is found, repair it and recheck the affected area.

---

# 2. Source boundary QA

Before translation, verify the exact requested range.

Check:

- requested section start
- requested section end
- next structural heading
- page boundaries
- whether unnumbered introductory text belongs to the requested unit
- whether unrelated next-section content was accidentally included

Do not assume section boundaries only from Session numbering.

Use:

- headings
- typography hierarchy
- table of contents
- surrounding pages
- document structure

If the boundary is uncertain, flag it before proceeding.

---

# 3. Translation completeness QA

Check every page for missing translation.

Verify:

- all requested body text is translated
- headings are translated
- captions are translated when safe
- explanatory labels are translated when appropriate
- footnotes are not accidentally omitted
- no paragraph is skipped
- no paragraph is duplicated
- no translated paragraph appears twice

Untranslated mathematical notation is expected.

Untranslated natural-language body text is not expected unless deliberately preserved.

---

# 4. Chinese language QA

Read the Chinese as Chinese.

Check for:

- machine-translation syntax
- English word order copied into Chinese
- unnatural long sentences
- awkward literal translation
- broken logical transitions
- unclear definitions
- unnatural instructional language
- excessive repetition
- inconsistent punctuation
- obvious spelling or wording errors

The result should resemble a professionally translated Chinese
mathematics textbook.

Do not improve style by changing mathematical meaning.

---

# 5. Terminology QA

If the project contains `glossary.json`, compare against it.

Check:

- established terms are used consistently
- one English term is not translated differently without reason
- different English terms are not collapsed into one Chinese term incorrectly
- newly introduced terms are recorded
- project-specific terminology remains consistent with earlier units

For uncertain terminology:

- inspect full context
- inspect earlier usage
- prefer standard mathematical Chinese
- do not guess

---

# 6. Formula preservation QA

Compare formulas directly with the source.

Check:

- variable names
- superscripts
- subscripts
- brackets
- equality signs
- inequality signs
- composition symbols
- arrows
- coordinates
- set notation
- indices
- identity maps
- inverse notation

No formula should be altered by translation.

---

# 7. Composition-order QA

Composition order is mathematically sensitive.

Explicitly inspect expressions such as:

`g ∘ f`

`r ∘ s`

`s ∘ r`

`h ∘ g ∘ f`

Check that:

- order is unchanged
- no expression is reversed
- associativity is not confused with commutativity
- regrouping has not changed ordering

Do not rely on memory.

Compare with the source.

---

# 8. Domain and codomain QA

For every mathematically important map, verify:

- source object
- target object
- arrow direction
- labels
- associated identity map

Examples:

`f : A → B`

`1_A`

`1_B`

Check that object names and identity subscripts are preserved.

---

# 9. One-sided inverse QA

When section/retraction or other one-sided inverse structures appear,
explicitly check them.

If the source states:

`r ∘ s = 1_A`

do not infer:

`s ∘ r = 1_B`

unless the source explicitly states it.

Verify:

- which map is the section
- which map is the retraction
- which composite equals the identity
- which object the identity belongs to

Do not promote a one-sided inverse into an isomorphism.

---

# 10. Isomorphism QA

If an isomorphism appears, verify both directions when required.

For example:

`g ∘ f = 1_A`

and

`f ∘ g = 1_B`

Check:

- composition order
- map direction
- identity subscripts
- wording

Do not translate "isomorphic" as "equal".

---

# 11. Idempotent QA

For idempotent maps, verify:

`e ∘ e = e`

Do not confuse this with:

`e ∘ e = 1_A`

or:

`e = 1_A`

Check any derivation producing an idempotent map from section/retraction data.

---

# 12. Element-level versus map-level QA

Check that the translation distinguishes:

- elements
- maps
- objects
- morphisms

Do not describe a complete map as if it were merely one element-to-element arrow.

Do not convert object-level statements into element-level statements unless the source does so.

---

# 13. Diagram QA

Treat diagrams as mathematics.

For every important diagram, verify:

- arrow origin
- arrow destination
- arrow direction
- object labels
- map labels
- point labels
- node relationships
- element correspondences
- coordinate order
- relative structure

Compare visually against the source.

---

# 14. Diagram-label QA

Check translated labels for:

- correct associated arrow
- correct associated node
- correct region
- correct axis
- correct object

Do not allow translated labels to:

- cover arrows
- cover nodes
- obscure intersections
- appear attached to the wrong object

If safe translation is impossible, preserve the original label and record it.

---

# 15. Inline math QA

Inspect every page containing Chinese text mixed with mathematics.

Check:

- formula baseline
- Chinese baseline
- formula vertical drift
- spacing before formulas
- spacing after formulas
- punctuation near formulas
- subscript/superscript clipping

Mathematical inline text should appear visually integrated with Chinese prose.

---

# 16. Parallel-formula alignment QA

This is a known high-risk issue.

For same-line structures such as:

`p ∘ s = 1_C    且    k ∘ s' = 1_B`

check that:

- both formulas share a visual baseline
- the Chinese connector is vertically aligned
- spacing is balanced
- neither formula appears higher or lower
- the complete line reads as one unit

Any obvious mismatch is a defect.

---

# 17. Display equation QA

For standalone equations, check:

- centering
- indentation
- spacing
- grouping
- derivation flow
- consistency with the source

Multi-line derivations should be inspected as a group.

---

# 18. Text box QA

Check every replaced text block for:

- clipping
- overflow
- overlap
- excessive empty space
- unnatural line breaks
- text covering formulas
- text covering diagrams

Do not assume that the original English box size is suitable for Chinese.

---

# 19. Page-layout QA

Inspect the whole page.

Check:

- title placement
- paragraph hierarchy
- page number
- image position
- equation position
- spacing balance
- visual reading order
- unusual blank regions
- shifted content

The translated page should still resemble the source page structurally.

---

# 20. Font QA

Check:

- Chinese glyphs render correctly
- no missing characters
- no square placeholders
- no garbled text
- Latin characters render correctly
- mathematical symbols remain intact
- font sizes are coherent

Avoid introducing inconsistent fonts without reason.

---

# 21. Searchability QA

When searchable text is expected, verify:

- Chinese can be selected
- Chinese can be copied
- Chinese can be searched
- translated text is not unintentionally rasterized

If the workflow intentionally rasterizes some elements, document it.

---

# 22. High-resolution visual QA

Render every translated page to high-resolution images.

Inspect every page visually.

For high-risk pages, zoom in significantly.

High-risk pages include:

- formula-heavy pages
- diagram-heavy pages
- pages with many arrows
- pages with parallel equations
- pages with dense inline math
- pages with many subscripts or superscripts
- pages where Chinese is much longer than English

Visual inspection is mandatory.

---

# 23. Source comparison QA

For mathematically important or visually complex pages:

compare:

source page

versus

translated page

side by side.

Check that no mathematical relationship has changed.

---

# 24. Untranslated English QA

Search for remaining English text.

Classify each occurrence as:

- mathematical notation
- proper name
- intentionally retained diagram label
- untranslated body text
- accidental omission

Only the first three may be acceptable.

Accidental untranslated body text must be fixed.

---

# 25. Duplicate and residual text QA

Check for:

- original English visible under Chinese
- duplicated Chinese overlays
- partial English remnants
- ghost text
- multiple text layers producing visual noise

Repair affected blocks locally.

---

# 26. Repair policy

When a problem is local, repair locally.

Prefer fixing:

- one sentence
- one text box
- one formula line
- one diagram label
- one page

Do not rerun the entire translation unit unless necessary.

After repair:

1. regenerate the affected output;
2. rerender the page;
3. inspect it again;
4. confirm the original defect is gone;
5. confirm the fix did not create a new defect.

---

# 27. Uncertainty handling

If any issue cannot be resolved confidently:

- inspect source context
- inspect previous page
- inspect next page
- inspect glossary
- inspect related diagrams

If uncertainty remains:

- preserve the source where appropriate
- mark the item for human review
- describe the uncertainty clearly

Do not fabricate a confident solution.

---

# 28. QA report

Each translation unit should produce a QA report.

The QA report should include:

- source page range
- processed page count
- translation completion status
- terminology changes
- preserved English labels
- mathematical issues found
- layout issues found
- fixes applied
- unresolved items
- pages requiring human review
- final QA result

Use severity labels when useful:

- CRITICAL
- MAJOR
- MINOR

---

# 29. Pass criteria

A translation unit passes QA only when:

- requested content is complete
- no known mathematical error remains
- formulas are preserved
- diagrams remain mathematically correct
- terminology is consistent
- Chinese is readable
- formula baselines are acceptable
- no major overlap or clipping remains
- every page has been visually inspected
- unresolved uncertainty is documented

---

# 30. Definition of done

A translation task is done only after:

translation

→ mathematical verification

→ layout verification

→ visual rendering

→ defect repair

→ final recheck

→ QA report

Generation alone is not completion.
