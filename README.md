# Academic Math PDF Translator

A reusable Agent Skill for translating academic and mathematical PDFs into high-quality Simplified Chinese while preserving mathematical meaning, notation, diagrams, terminology, layout, and visual quality.

This Skill is designed for:

- mathematics textbooks
- category theory texts
- physics and mathematical physics
- technical lecture notes
- academic papers
- equation-heavy PDFs
- diagram-heavy academic documents

It is not intended as a general-purpose literary translation workflow.

---

## What this Skill does

The Skill provides a reusable workflow for mathematical PDF translation.

It focuses on:

1. mathematical semantic correctness
2. formula and notation preservation
3. diagram correctness
4. terminology consistency
5. natural Simplified Chinese
6. mathematical typography
7. preservation of the source PDF structure
8. mandatory QA and visual inspection
9. local repair of translation or layout defects

The goal is not simply to replace English text with Chinese.

The goal is to produce a translated mathematical PDF that remains mathematically correct, visually readable, and structurally faithful to the source.

---

## Repository structure

```text
Academic-math-pdf/
├─ SKILL.md
├─ README.md
├─ references/
│  ├─ translation-rules.md
│  ├─ math-layout-rules.md
│  └─ qa-checklist.md
└─ templates/
   └─ session-task.md
```

---

## Files

### `SKILL.md`

The main Skill definition.

It defines:

- when the Skill should be used
- the overall translation workflow
- project-state handling
- mathematical preservation rules
- PDF production principles
- QA requirements
- repair policy
- completion criteria

It also instructs the agent to read the supporting files in this repository.

---

### `references/translation-rules.md`

Defines how mathematical prose should be translated.

It covers:

- natural Chinese mathematical language
- terminology consistency
- logical fidelity
- preservation of abstraction level
- definitions
- implications
- mathematical distinctions
- avoidance of machine-translation syntax
- context-sensitive terminology
- instructional tone
- ambiguity handling

---

### `references/math-layout-rules.md`

Defines mathematical typography and PDF layout requirements.

It covers:

- inline formula alignment
- formula baselines
- parallel equations
- Chinese connectors between formulas
- subscripts and superscripts
- text-box adjustment
- diagram labels
- line wrapping
- formula groups
- visual QA

A known high-risk issue is same-line formula baseline mismatch.

For example:

```text
p ∘ s = 1_C    且    k ∘ s' = 1_B
```

The two formulas and the Chinese connector must appear as one visually coherent line.

A mathematically correct but visibly misaligned formula line is considered a layout defect.

---

### `references/qa-checklist.md`

Defines the mandatory QA process.

QA includes:

- source-boundary verification
- translation completeness
- Chinese-language quality
- terminology consistency
- formula preservation
- composition order
- domains and codomains
- one-sided inverses
- isomorphisms
- idempotents
- diagrams
- formula baselines
- text overflow
- font rendering
- searchability
- high-resolution visual inspection
- source-versus-output comparison
- local defect repair

PDF generation alone is not considered completion.

---

### `templates/session-task.md`

A reusable task template for bounded translation units.

It can be used for:

- Sessions
- chapters
- sections
- articles
- introductions
- appendices
- unnumbered texts
- other named document units

The template defines:

- unit boundaries
- project continuity
- mathematical risks
- terminology handling
- PDF production
- QA
- output naming
- progress updates
- stop conditions

---

## Recommended architecture

This repository should contain reusable translation behavior.

Book-specific information should remain in a separate project.

For example:

```text
Conceptual-Mathematics-CN/
├─ project.md
├─ glossary.json
├─ translation_style.md
├─ progress.json
├─ original/
├─ output/
└─ qa/
```

The separation is:

```text
Skill = reusable translation method

Project = book-specific state

Task = current translation unit
```

This keeps the Skill reusable across different books.

---

## Project-specific files

### `project.md`

Describes the current translation project.

It may define:

- source book
- project goals
- translation units
- chapter or Session structure
- special workflow rules
- output conventions

---

### `glossary.json`

Stores authoritative terminology for the current book or project.

Example:

```json
{
  "set": "集合",
  "element": "元素",
  "map": "映射",
  "morphism": "态射",
  "domain": "定义域",
  "codomain": "陪域",
  "image": "像集",
  "composition": "复合",
  "identity map": "恒等映射",
  "inverse map": "逆映射",
  "isomorphism": "同构",
  "section": "截面",
  "retraction": "回缩",
  "idempotent": "幂等"
}
```

The project glossary takes precedence over generic translation choices.

---

### `translation_style.md`

Stores project-specific style decisions.

Examples:

- terminology conventions
- title conventions
- punctuation preferences
- first-occurrence terminology rules
- diagram-label policy
- PDF-layout conventions

---

### `progress.json`

Stores project state.

Typical fields may include:

- completed units
- current unit
- source page ranges
- output PDF names
- QA report names
- newly introduced terminology
- unresolved issues
- human-review items
- QA status

---

## Typical workflow

A translation run should follow this structure:

```text
source PDF
    ↓
read Skill
    ↓
read supporting rules
    ↓
read project state
    ↓
detect requested unit
    ↓
translate natural language
    ↓
preserve mathematical content
    ↓
generate translated PDF
    ↓
mathematical QA
    ↓
layout QA
    ↓
high-resolution visual QA
    ↓
local defect repair
    ↓
final recheck
    ↓
QA report
    ↓
update project state
```

---

## Example usage

Instead of writing a long translation prompt every time, the user can make a short request such as:

```text
Use the Academic Math PDF Translator Skill.

Continue the Conceptual Mathematics translation project with Session 10.

Read the existing project glossary, translation style, progress state,
and previous workflow.

Translate only Session 10 and stop before Session 11.
```

The agent should then:

1. read `SKILL.md`;
2. read all relevant supporting files;
3. inspect the project state;
4. locate Session 10;
5. locate the beginning of Session 11;
6. translate exactly that interval;
7. preserve formulas and diagrams;
8. generate the translated PDF;
9. perform full QA;
10. repair local defects;
11. update project state;
12. stop before Session 11.

---

## Mathematical integrity

Mathematical content must not be altered during translation.

Preserve:

- variable names
- object names
- map names
- arrow direction
- composition order
- subscripts
- superscripts
- equations
- coordinates
- diagrams
- identity-map subscripts

For example:

```text
g ∘ f
```

must not silently become:

```text
f ∘ g
```

Likewise:

```text
e ∘ e = e
```

must not be confused with:

```text
e ∘ e = 1_A
```

---

## Translation philosophy

The translation should preserve mathematical meaning rather than English surface syntax.

The preferred objective is:

```text
mathematical correctness
+
logical fidelity
+
terminology consistency
+
preservation of abstraction
+
natural Chinese
+
clean mathematical layout
```

The translated output should read like a professionally translated Chinese mathematical textbook.

It should not read like raw machine translation.

---

## Diagram policy

Mathematical diagrams are treated as mathematical content.

The workflow must preserve:

- arrow direction
- arrow endpoints
- nodes
- object positions
- map labels
- element correspondences
- graph structure
- coordinate relationships

If translating a diagram label risks damaging the mathematical structure, preserving the original label is preferable.

---

## Layout policy

The workflow must inspect the rendered PDF visually.

Do not rely only on:

- extracted text
- PDF coordinates
- script success
- bounding-box collision tests

Special attention should be given to:

- inline formulas
- parallel formulas
- Chinese/math baseline alignment
- dense formula pages
- diagrams
- arrows
- superscripts
- subscripts
- translated text that is significantly longer than the source

---

## QA policy

A translation is complete only after:

```text
translation
→ mathematical verification
→ terminology verification
→ layout verification
→ visual rendering
→ defect repair
→ final recheck
→ QA report
```

If a local defect is found, repair the affected block or page rather than rerunning the whole translation unit whenever possible.

---

## Uncertainty policy

Do not guess.

When a mathematical term, formula, diagram, or source sentence is uncertain:

1. inspect the local source;
2. inspect surrounding paragraphs;
3. inspect adjacent pages;
4. inspect the glossary;
5. inspect previous translated units;
6. inspect related diagrams.

If uncertainty remains, preserve the source where appropriate and flag the issue for human review.

---

## Priority order

When requirements conflict, use this priority:

1. mathematical semantic correctness
2. mathematical diagram correctness
3. formula and notation correctness
4. logical fidelity
5. terminology consistency
6. preservation of abstraction level
7. mathematical typography
8. natural Chinese readability
9. visual polish

---

## Scope

This Skill is intentionally focused on mathematical and academic PDF translation.

It is not intended to optimize:

- literary translation
- creative writing
- subtitles
- marketing localization
- casual web-page translation

Different translation domains require different optimization criteria.

---

## Design principle

Keep reusable behavior in the Skill.

Keep book-specific information in the project.

Do not hard-code:

- one book's terminology
- one book's Session structure
- one project's progress
- one textbook's special conventions

into the reusable Skill unless they are genuinely generalizable.

This allows the same Skill to be reused for many mathematical and academic PDF projects.