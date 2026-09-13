# Translation Rules

These rules define the translation behavior for academic and mathematical PDF localization into Simplified Chinese.

They complement:

- `SKILL.md`
- `references/math-layout-rules.md`
- `references/qa-checklist.md`

The purpose of this document is to define how mathematical prose should be translated while preserving meaning, terminology, logical structure, and readability.

---

# 1. Core objective

Translate mathematical meaning, not isolated words.

The output should read like a professionally translated Chinese mathematics textbook.

A good translation must simultaneously preserve:

- mathematical correctness
- logical structure
- terminology
- pedagogical intent
- source meaning
- natural Chinese readability

Literal correspondence is not the goal.

Semantic fidelity is the goal.

---

# 2. Do not translate word by word

Avoid direct word-for-word translation when it produces unnatural Chinese.

English and Chinese differ in:

- word order
- subject usage
- clause structure
- connective usage
- repetition
- paragraph rhythm

You may restructure a sentence when necessary for natural Chinese.

However, restructuring must not alter mathematical meaning.

---

# 3. Preserve logical strength

Never weaken or strengthen a mathematical statement during translation.

Preserve distinctions such as:

- if
- only if
- if and only if
- necessary
- sufficient
- every
- some
- unique
- at least one
- at most one
- exactly one

Do not replace precise mathematical language with vague prose.

---

# 4. Preserve implication direction

Statements of the form:

`If P, then Q`

must remain logically equivalent to:

`P → Q`

Do not accidentally reverse the implication.

Do not translate:

`P implies Q`

as if it meant:

`Q implies P`.

---

# 5. Preserve definitions

Definitions must remain definitions.

If the source says:

“We call ...”

or:

“By ... we mean ...”

translate it with wording appropriate for a mathematical definition.

Examples may include:

- “称……为……”
- “所谓……，是指……”
- “我们把……称为……”

Choose according to context.

Do not turn a formal definition into casual explanation.

---

# 6. Preserve distinctions

When the author distinguishes two concepts, preserve the distinction.

Examples include:

- object versus element
- map versus element correspondence
- equality versus isomorphism
- domain versus codomain
- codomain versus image
- inverse versus one-sided inverse
- section versus retraction
- identity versus idempotent
- object versus coordinate representation

Do not collapse related concepts merely because Chinese wording is similar.

---

# 7. Mathematical terminology

If `glossary.json` exists, it is authoritative.

Use established project terminology consistently.

Before translating a new technical term:

1. inspect the full local context;
2. inspect earlier usage;
3. check the project glossary;
4. prefer standard Chinese mathematical terminology;
5. avoid inventing unnecessary new translations.

If multiple Chinese translations are common, choose one and keep it stable within the project.

---

# 8. Context-dependent terminology

Do not translate a technical English word solely from its dictionary meaning.

Words such as:

- map
- point
- image
- section
- retraction
- representation
- product
- graph
- object
- structure

may have technical meanings determined by mathematical context.

Read the surrounding paragraphs before deciding.

---

# 9. First occurrence of difficult terms

For important or potentially ambiguous terms, the first occurrence may use:

Chinese translation + English term

for example:

`幂等映射（idempotent map）`

if this improves clarity.

Do not repeat English parentheses unnecessarily throughout the text unless the project style requires it.

---

# 10. Natural Chinese mathematical prose

Prefer standard Chinese mathematical writing.

Common structures may be translated naturally.

Examples:

`Suppose that...`

may become:

- “设……”
- “假设……”

`Notice that...`

may become:

- “注意……”
- “注意到……”

`It follows that...`

may become:

- “因此……”
- “由此可得……”
- “于是……”

`In other words...`

may become:

- “换句话说……”
- “也就是说……”

`For example...`

usually becomes:

- “例如……”
- “比如……”

Do not force one fixed translation for every occurrence.

---

# 11. Avoid machine-translation syntax

Reject Chinese that sounds like English syntax with Chinese words substituted.

Typical problems include:

- unnecessary explicit subjects
- excessive passive constructions
- repeated pronouns
- unnatural connective stacking
- overly long sentences
- direct copying of English clause order

Rewrite locally when needed.

---

# 12. Long sentences

English mathematical prose may contain long nested sentences.

When appropriate, divide one English sentence into two or more Chinese sentences.

Allowed:

- splitting a sentence
- changing clause order
- moving explanatory material
- replacing English punctuation with Chinese punctuation

Not allowed:

- changing logical relationships
- dropping conditions
- changing scope
- changing quantifiers
- adding interpretation

---

# 13. Short fragmented sentences

Some English textbooks use many short instructional sentences.

Chinese may sometimes read better when closely related fragments are combined.

Combination is allowed only when the logical relationship remains obvious.

Do not combine statements that the author intentionally separates for emphasis.

---

# 14. Questions

Preserve the pedagogical role of questions.

If the author asks the reader a question, do not automatically convert it into a declarative statement.

Maintain:

- exploratory questions
- rhetorical questions
- exercises embedded in prose
- prompts for observation

The translation should preserve the teaching rhythm.

---

# 15. Author voice

Preserve the author's tone.

If the source is:

- conversational
- exploratory
- formal
- concise
- instructional

the Chinese should reflect that style.

Do not make every paragraph sound like a modern AI-generated textbook summary.

---

# 16. Do not over-explain

Do not add explanations merely because the concept is difficult.

Do not add:

- examples
- analogies
- background knowledge
- philosophical comments
- historical comments
- extra definitions
- explanatory footnotes

unless the user explicitly requests them.

The translation is not a commentary edition.

---

# 17. Do not simplify mathematical abstraction

Do not translate abstract categorical or structural language back into elementary element-level language unless the author does so.

For example:

a statement about a map as a morphism should not automatically become a description of “each element moving to another element”.

Preserve the mathematical level of abstraction.

---

# 18. Element-level and morphism-level language

Distinguish carefully between expressions such as:

`f(x)`

and:

`f`

The first concerns the action of a map on an element.

The second concerns the map itself.

Do not blur this distinction.

---

# 19. Equality and isomorphism

Do not translate:

`isomorphic`

as:

`equal`

Two objects may be isomorphic without being literally the same object.

Preserve this distinction consistently.

---

# 20. Maps and arrows

In ordinary explanatory prose, use the project-approved translation for `map`.

If the project uses:

`map → 映射`

retain it consistently.

If `morphism` appears, use the project-approved term such as:

`态射`

when appropriate.

Do not casually alternate between technical terms without reason.

---

# 21. Domain, codomain, and image

Preserve these distinctions carefully.

Typical project terminology:

- domain → 定义域
- codomain → 陪域
- image → 像集

Do not translate codomain as image.

Do not translate image as codomain.

---

# 22. Composition

Composition order must remain exact.

For:

`g ∘ f`

the mathematical meaning is:

first `f`, then `g`.

Do not translate prose in a way that reverses this order.

Whenever composition is discussed verbally, compare the Chinese sentence against the formula.

---

# 23. Identity maps

Preserve object-specific identity maps.

Examples:

`1_A`

`1_B`

Do not remove or alter subscripts.

Translate explanatory prose naturally while keeping the mathematical distinction visible.

---

# 24. One-sided inverses

For section/retraction structures, preserve exactly which composite equals an identity.

If:

`r ∘ s = 1_A`

do not imply:

`s ∘ r = 1_B`

unless the source explicitly establishes it.

Do not translate a one-sided inverse relationship as full invertibility.

---

# 25. Idempotents

For idempotent maps:

`e ∘ e = e`

must remain distinct from:

`e = 1_A`

and:

`e ∘ e = 1_A`.

Do not describe idempotence as identity unless the source explicitly proves equality.

---

# 26. Coordinates and representations

Distinguish:

- an object
- its coordinate representation
- a map connecting them

Do not translate:

“represented by coordinates”

as:

“is identical to the coordinates”.

Preserve representation versus identity.

---

# 27. Examples

Examples must remain examples.

Do not silently generalize an example into a theorem.

Do not translate phrases such as:

“for example”

in a way that makes the following statement sound universal.

---

# 28. Theorems and claims

Preserve structural labels such as:

- theorem
- proposition
- lemma
- corollary
- definition
- example
- exercise

Use project conventions if available.

Do not invent formal labels when the source does not contain them.

---

# 29. Proof language

If proofs appear, preserve the logical sequence.

Common proof expressions should be translated naturally.

Examples:

`Therefore`

may become:

- “因此”
- “所以”
- “由此”

`Hence`

may become:

- “因此”
- “于是”

`This shows that`

may become:

- “这说明……”
- “由此可见……”

Choose according to context.

---

# 30. Ambiguity

If the source sentence is mathematically ambiguous:

do not resolve the ambiguity by invention.

Instead:

1. read surrounding context;
2. inspect related formulas;
3. inspect diagrams;
4. inspect earlier definitions;
5. consult glossary and project notes.

If uncertainty remains, flag the issue for review.

---

# 31. Proper names

Preserve internationally standard proper names and established Chinese forms.

For mathematicians, places, named theorems, and historical names:

prefer established Chinese translations when confidently known.

If uncertain, preserve the original name rather than inventing a transliteration.

---

# 32. Titles

Translate titles naturally but preserve their structural meaning.

Do not force titles into overly literary Chinese.

For technical chapter titles, clarity and terminology consistency have priority.

---

# 33. Unnumbered texts

Translate meaningful unnumbered content when it belongs to the requested source range.

Do not skip:

- introductions
- interludes
- short essays
- explanatory notes
- Part introductions
- unnumbered section texts

merely because they lack a Session or chapter number.

---

# 34. Captions

Translate figure and table captions when they contain natural language and can be translated safely.

Preserve:

- numbering
- mathematical symbols
- object labels
- references

If the caption is tightly integrated into a mathematical diagram and translation risks damage, preserve the source and note it in QA.

---

# 35. Parentheses

Do not mechanically preserve English parentheses if Chinese punctuation would read more naturally.

However, mathematical parentheses and grouping symbols must never be altered for stylistic reasons.

Distinguish linguistic punctuation from mathematical syntax.

---

# 36. Punctuation

Use natural Simplified Chinese punctuation in prose.

Preserve mathematical punctuation where it is part of notation.

Avoid mixing Chinese and English punctuation inconsistently.

---

# 37. Repetition

English mathematical prose sometimes repeats nouns where Chinese naturally omits them.

Reasonable omission is allowed if reference remains unambiguous.

Do not remove repetition when it carries mathematical precision.

---

# 38. Pronouns

Chinese often requires fewer explicit pronouns than English.

You may omit repeated:

- it
- this
- they
- we

when Chinese remains clear.

However, never create ambiguity about mathematical referents.

---

# 39. “We”

Mathematical English frequently uses “we”.

Translate naturally according to context.

Possible strategies include:

- “我们……”
- omitting the subject
- using an imperative or neutral mathematical construction

Do not mechanically translate every “we” as “我们”.

---

# 40. Passive voice

English academic writing often uses passive voice.

Chinese may use active or subjectless constructions when more natural.

You may change grammatical voice if mathematical meaning remains identical.

---

# 41. Translation consistency across sessions

Treat the book or project as one continuous translation.

Do not translate each Session independently as if prior Sessions did not exist.

Use:

- glossary
- translation style
- previous translated units
- project state

to maintain continuity.

---

# 42. Do not silently revise earlier terminology

If a later section reveals that an earlier glossary choice is suboptimal:

do not silently change the term.

Instead:

1. record the issue;
2. propose the correction;
3. identify affected previous units;
4. update consistently only when appropriate.

---

# 43. Translation priority

When linguistic choices conflict, use this order:

1. mathematical semantic correctness
2. logical fidelity
3. terminology consistency
4. preservation of abstraction level
5. source tone and pedagogical intent
6. natural Chinese readability
7. stylistic elegance

Elegant Chinese must never come at the cost of mathematical precision.

---

# 44. Final reread

Before accepting a translated block:

read the Chinese without looking at the English.

Ask:

- Does this sound like natural Chinese mathematics?
- Can the logical relationship be understood?
- Are technical terms consistent?
- Does anything sound mechanically translated?

Then compare again with the English source.

Both tests must pass.

---

# 45. Definition of acceptable translation

A translation passes only when:

- mathematical meaning is preserved;
- logical relationships are preserved;
- terminology is consistent;
- abstraction level is preserved;
- no important information is omitted;
- no unsupported information is added;
- Chinese reads naturally;
- the author's instructional role is preserved.