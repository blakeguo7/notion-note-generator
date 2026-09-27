---
name: notion-note-generator
license: MIT
description: Turn websites, slide decks, PDFs, documents, and supplied learning material into source-grounded notes and create or update them in Notion. Use when the user wants to study, synthesize, reorganize, or preserve knowledge in Notion; do not use for meeting notes, task tracking, or general Notion administration.
---

# Notion Note Generator

Produce source-grounded teaching notes that a learner can follow from their existing knowledge to a new understanding. Preserve the reasoning between ideas, not just the ideas themselves, while keeping claims traceable to the actual sources.

## Default writing standard

- Default to self-contained lecture-style notes for first-time learning at the intended audience's level. Use a concise treatment, revision outline, or reference format when the user requests it; do not let a recap replace the teaching in a substantial learning note.
- Organize around a connected line of explanation. Establish needed prerequisites and make clear why each important concept follows from what the learner has just understood. Topic coverage alone is not evidence of understanding.
- Balance completeness and information density by removing repetition and tangents, not intermediate reasoning. Use connected prose to explain mechanisms and relationships; reserve lists and tables for genuine parallel items, comparisons, procedures, and recaps.
- Use examples that expose the mechanism with enough context to follow it. Prefer developing one example through related concepts over restarting with an unrelated miniature example at every heading. Do not force examples where they add no understanding.
- For technical notes, preserve the English terminology needed to learn and communicate the subject accurately. Use standard English terms directly where they read naturally instead of forcing a Chinese translation. Use bilingual clarification only when it genuinely helps the learner identify an unfamiliar concept.
- Apply the same terminology standard to the page title and every heading level, not only to body text. When a title or heading names a technical concept, retain its standard English term or use the same bilingual identification rather than defaulting to Chinese-only wording.

## Workflow

1. Establish the learning goal, supplied sources, intended audience, language, and Notion destination from the request and available context. Ask only when a missing destination or hierarchy choice would materially change the result.
2. Inspect the actual source content before outlining:
   - For a website, open the relevant pages rather than relying on search snippets.
   - For slides or PDFs, inspect extracted text and the rendered pages needed to understand diagrams, tables, or layout.
   - For multiple sources, keep a lightweight source map so important claims can be traced back to a URL, file, page, or slide.
   - State inaccessible material and partial coverage; never imply that an unread source was reviewed.
3. Fetch the target Notion page and its relevant hierarchy before planning an update. For a new destination, locate and confirm the intended parent or data source.
4. Read [references/note-design.md](references/note-design.md) before structuring or drafting substantial learning notes. Plan the learner's starting knowledge, intended understanding, and the reasoning steps connecting them before choosing headings. Group pages into complete teaching units; do not split a dependent explanation merely because it introduces another term. Use a compact hub for several substantial learning threads. A requested Notion page is a real page, not merely a heading.
5. Draft source-grounded explanations along that learning path. Preserve the source's meaning, separate sourced facts from interpretation or added explanation, and attach useful source links or page/slide references. Supplement the user's sources only when requested or needed to resolve a material ambiguity, and label the added source. Before delivery or a Notion write, apply the teaching-quality check in the design reference; repair missing reasoning and unexplained prerequisites, not just formatting or coverage.
6. Write only when the user requested Notion creation or editing. Follow [references/notion-writing.md](references/notion-writing.md) for tool checks, safe updates, hierarchy handling, and post-write verification. If the user asked only for a draft or outline, return it without changing Notion.
7. Fetch the written pages and affected parent after the write. Verify titles, placement, hierarchy, duplicate links/pages, source references, code blocks, tables, and requested coverage before reporting completion.

## Output expectations

- Lead with the central idea and organize details around questions the learner should be able to answer.
- Prefer explanations, meaningful examples, request or process flows, responsibility boundaries, and common misconceptions over copied source wording.
- Do not collapse substantial source material into a shallow outline, and do not inflate notes with repeated phrasing or exhaustive side details.
- Keep navigation pages compact. Each teaching page should develop a complete learning question, with enough prerequisite context or an explicit prerequisite link to be understandable when opened independently.
- Preserve uncertainty, conflicts between sources, historical context, and source-specific terminology.
- Return the created or updated Notion page links and briefly identify any unread sources or unresolved gaps.

## Boundaries

- Do not claim Notion access merely because a plugin is installed; confirm that the current session exposes usable Notion tools.
- Do not create a duplicate page when a write result is uncertain. Search or fetch the destination before retrying.
- Do not overwrite unrelated content, unknown blocks, or existing child-page links.
- Do not force every source into the same template. Match the structure to the material and the user's learning purpose.
