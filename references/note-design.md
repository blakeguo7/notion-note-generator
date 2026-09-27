# Learning-note design

Use this reference when the material is substantial enough to require an outline, page hierarchy, or teaching-oriented rewrite.

## Plan the understanding path

Before choosing headings for a substantial note, establish the learner's starting knowledge, the question they should be able to answer by the end, and the intermediate reasoning needed to get there. Keep this planning lightweight; it need not appear as a separate deliverable unless requested.

Choose an explanatory relationship that fits the material: a problem and its solution, a process from input to output, a whole and its parts, a comparison, or a chain of dependencies. Do not turn this into a mandatory problem-solution template. Source order is useful only when it also supports the learner's understanding.

Identify prerequisites at the point where they become necessary. Explain a missing prerequisite briefly or point to the relevant earlier lesson; do not silently depend on concepts the intended learner has not encountered.

## Choose the smallest complete teaching unit

- Use a single page when one source covers one focused idea and remains easy to review as a unit.
- Use a compact hub plus child pages when the material contains distinct, substantial learning questions. A new term alone is not a reason for a new page; keep a dependent explanation and its worked example together.
- Group by the knowledge chain and learner questions, not mechanically by file count, slide section, or source order.
- Keep the hub to a short orientation and navigation. Each child page should state enough starting context or link its prerequisites to make sense when opened independently. In a sequence, briefly connect the current question to what the previous page established without repeating that lesson.
- Put child-page links in a compact navigation block near the top of every hub or chapter page, immediately after any brief orientation. Do not make users scroll through substantial body content to find the page navigation.
- Do not represent a requested child page as an H2 section. Create or update an actual Notion page and verify its parent relationship.

## Develop a connected explanation

Introduce an important concept when the learner can see its role in the current question. Explain the reasoning that leads to a conclusion instead of presenting a definition, a use case, and a caveat as disconnected entries. Between related sections, make the relationship explicit: what is now understood, what remains unresolved, or how the next part fits the whole. A generic sentence such as "Next, we introduce X" does not supply that relationship.

Use connected paragraphs for reasoning and explanation. Lists work well for parallel properties, comparisons, steps, and recaps, but a succession of short headed lists is not a lecture. Turning each bullet into a one-sentence paragraph does not repair the missing reasoning. Avoid fixed word counts, paragraph quotas, or a repeated set of headings for every concept.

### Extend examples instead of resetting them

For related ideas, carry one concrete scenario through the explanation: establish a baseline, trace what happens, expose a relevant limitation or variation, and show how the new idea changes the result. Introduce new machinery only as needed to explain that change. Use a different example when the topic genuinely changes or a contrast reveals something the first example cannot.

For code, establish its purpose and inputs before showing it. Explain the important intermediate values, responsible components, and resulting output; connect unfamiliar symbols to the concept they implement. Distinguish a runnable example from a fragment and identify omitted setup. Prefer the smallest meaningful change to the running example over repeatedly dropping in unrelated complete programs. Syntax validity alone does not show that the code has been taught.

Use a diagram when a relationship or flow is easier to see than to infer from prose. Explain what its components and connections represent, and trace the same example through it. A diagram or code block supplements the explanation; it does not replace it.

### Control depth without breaking the reasoning

Teach the central mechanism before optional advanced details. Include a boundary or caveat early when it is necessary to avoid a false mental model; defer unrelated optimization, production concerns, and additional terminology until the core question is resolved. Provide an interview-ready recap only when interview preparation is part of the user's goal.

A note is sufficiently detailed when the learner can follow the main reasoning and reconstruct the explanation without reopening the original source. Add detail where a reasoning step is missing, not to meet a length target. Stop when additional material is repetitive, tangential, or unlikely to improve understanding. A concise end recap can support later review after the explanation has done the teaching.

### Contrast: coverage versus teaching

The following is an illustrative explanation of a merge rule, not documentation for a particular library or a template to copy into unrelated lessons.

Coverage-only outline:

> A reducer combines an old value and an update. It can replace or append values. Different fields need different rules.

Connected teaching:

> Suppose our program has already collected document A. Its next step finds document B. Before storing that result, we need to decide what the field should contain afterward: only B, or both A and B? Receiving a new value does not, by itself, answer that question.
>
> The answer depends on what the field means. For a current status, a new value such as "finished" should replace "running". For collected documents, replacing the list would lose A, so this example needs to retain the old documents and add the new ones. The two fields need different update rules.
>
> We can express such a rule as a reducer: a function that takes the old value and the incoming update and returns the next value. For our document example, concatenating old `[A]` with incoming `[B]` produces `[A, B]`; replacement would produce `[B]`. We can now examine the implementation with a specific question in mind: where is that field's rule chosen and applied?

The improvement is the visible decision and worked consequence, not the extra length or transition words. Any library-specific defaults and behavior still need to be established from the actual source.

## Technical terminology

- Preserve established English technical terms, especially for APIs, protocols, architectural patterns, algorithms, packages, classes, functions, and identifiers.
- In Chinese technical notes, use an English term directly when that is the natural and commonly recognized form; do not manufacture or force a Chinese translation.
- When a Chinese explanation benefits from bilingual identification, introduce the term as `中文术语（English Full Name，Abbreviation）` on first occurrence. Omit the abbreviation when none is standard, and do not repeat the full annotation later.
- If an abbreviation would be unclear on its own, provide its English full name on first occurrence.
- Keep code symbols and official product or library names exactly as written by their source.

## Preserve source fidelity

- Use the user's supplied material as the primary evidence.
- Cite a website with its direct URL. For a deck or PDF, retain the filename and useful slide/page numbers.
- Distinguish direct source content, your explanatory synthesis, and any inference that is not stated explicitly.
- Label dated or historical figures instead of presenting them as current facts.
- If sources disagree, preserve the disagreement and its scope rather than silently choosing one.
- Avoid copying large passages. Condense, connect, and explain.

## Teaching-quality check

Before delivering a substantial draft or writing it to Notion, read it in sequence from the intended learner's perspective:

- Can the learner tell why each important concept appears here and how it relates to what came before? Repair unexplained jumps rather than adding generic transition phrases.
- Are prerequisites and newly introduced terms explained or explicitly linked before the reasoning depends on them?
- Is each central conclusion supported by an explanation, derivation, or worked example? For a mechanism or process, can the learner trace input through the important intermediate steps to output and predict the effect of a simple variation?
- If there is code or a diagram, can the learner connect its important elements to the explanation rather than merely recognize its labels?
- If the headings and formatting were removed, would the body still contain a connected explanation, or only disconnected facts? A glossary or revision sheet requested by the user is an intentional exception.
- Does the note answer its central question while preserving source traceability, uncertainty, and the user's requested depth, without repeated lessons or advanced tangents?

Revise actual gaps in the reasoning before delivery. Coverage, length, source links, valid code, and correct Notion hierarchy are useful checks, but none alone establishes teaching quality. Do not add boilerplate sections merely to make every check visible in the note.
