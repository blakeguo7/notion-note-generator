# Safe Notion writing

Use this reference whenever the task will create, update, move, or reorganize Notion pages.

## Confirm access and destination

1. Inspect the actual tools available in the current session. An installed Notion plugin does not prove that its tools are connected or authorized.
2. If Notion tools are unavailable, do not claim a write. Preserve a Notion-ready draft when useful and tell the user what connection or authorization is missing.
3. Search for and fetch the destination before editing. If several plausible parents or databases remain, ask the user to choose rather than guessing a hierarchy that will require cleanup.
4. Pass only Notion page, database, or data-source IDs and URLs to Notion fetch operations. External-source URLs belong in the note as sources, not as Notion fetch targets.

Tool names and schemas can vary by connector version. Follow the live tool schema. Common operations include `Notion:search`, `Notion:fetch`, `Notion:notion-create-pages`, and `Notion:notion-update-page`.

## Create safely

- Create pages with an explicit parent and the title/properties required by that parent or data source.
- Create one coherent knowledge unit at a time when hierarchy or placement needs verification.
- A successful create response does not prove correct placement. Fetch the new page and its parent, then verify the relationship and visible link.
- If the response is missing or ambiguous, search or fetch before retrying. Do not create another page until absence is confirmed.

## Update safely

- Fetch the current page immediately before changing it.
- Prefer a narrow content update that preserves unrelated blocks and child-page links.
- When the connector uses search-and-replace updates, copy `old_str` exactly from the fetched Markdown. Supply required empty fields such as `properties: {}` or `content_updates: []` when the live schema requires them.
- If an update returns `No matches found`, re-fetch the page, copy the exact live fragment, and retry once with a smaller replacement. If it still fails, stop and report the conflict instead of broadening the rewrite.
- Reuse existing child pages when they already represent the intended topic. Do not create duplicates just to avoid a difficult edit.
- Page creation may append a child link at the end of the parent. Move each existing child link into a compact navigation section near the top of the parent, after any brief orientation and before substantial body content. Preserve the intended order and confirm that each child page ID appears exactly once.

## Verify after writing

Fetch every created or updated page and the affected parent. Check:

- exact title and intended parent;
- child-page navigation near the top, intended order, and one visible link per child page;
- preservation of unrelated neighboring content;
- source links and page/slide references;
- code-block languages, tables, callouts, and lists;
- absence of unresolved connector errors or duplicate pages.

Report completion only after this read-back matches the requested structure and content.
