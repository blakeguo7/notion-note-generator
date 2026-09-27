# Notion Note Generator

English | [简体中文](README.zh-CN.md)

A Codex skill for turning websites, slide decks, PDFs, and documents into source-grounded learning notes in Notion.

The skill builds connected explanations: establish the learner's starting point, explain how ideas follow from one another, develop meaningful examples, and keep claims traceable to the original material.

## What it does

- Reads the actual sources before planning notes and identifies unread or inaccessible material.
- Explains mechanisms, prerequisites, and relationships at the learner's level.
- Preserves standard English technical terminology, with bilingual clarification when useful.
- Organizes substantial topics into complete teaching pages with compact navigation.
- Creates or updates Notion pages when requested, preserving unrelated content and existing child-page links.
- Reads back written pages and their parents to verify content and placement.

You can also request a draft or outline without changing Notion.

## Requirements

- Codex with local skills support.
- Tools that can read the supplied sources. Slides and PDFs may require both text extraction and rendered-page inspection.
- For Notion writes, a connected Notion integration with access to the destination page. The dependency declared in `agents/openai.yaml` does not establish an authenticated connection by itself.

## Installation

Download this repository and keep the complete folder, including `agents/` and `references/`.

For personal use, place it at:

```text
~/.agents/skills/notion-note-generator/
```

For use within one project, place it at:

```text
<project>/.agents/skills/notion-note-generator/
```

If you already have a copy installed, compare the versions before replacing it. Codex detects skill changes automatically; restart Codex if the skill does not appear.

You can also ask the built-in `$skill-installer` to install from this repository's GitHub URL. Tell it that `SKILL.md` is at the repository root and the skill name is `notion-note-generator`.

```text
$skill-installer
Install the skill from https://github.com/blakeguo7/notion-note-generator.
SKILL.md is at the repository root. Use notion-note-generator as the skill name.
```

See the official [Codex skills documentation](https://developers.openai.com/codex/skills) for installation locations and supported metadata.

## Usage

Invoke `$notion-note-generator` in Codex and provide your sources, learning goal, current knowledge, preferred language, and destination when writing to Notion.

**Create learning notes**

```text
$notion-note-generator
Use the attached lecture slides to teach me how GPU memory hierarchy affects
program execution. I know basic Python but am new to GPU programming.
Write the notes in Chinese, retain standard English technical terms, and
create them under this Notion page: <Notion parent page URL>.
```

**Update existing notes**

```text
$notion-note-generator
Use these official documentation URLs to improve the explanations and
examples on <Notion page URL>. Preserve unrelated content and child pages,
and identify any differences between the existing notes and the sources.
```

**Draft first**

```text
$notion-note-generator
Use this PDF to draft beginner-friendly learning notes in Chinese. Retain
standard English technical terms, explain how the concepts relate, and cite
source page numbers. Return the draft without changing Notion.
```

## Files

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Skill scope, writing standard, and workflow |
| [references/note-design.md](references/note-design.md) | Teaching structure, examples, terminology, and quality checks |
| [references/notion-writing.md](references/notion-writing.md) | Destination checks, focused updates, and read-back verification |
| [agents/openai.yaml](agents/openai.yaml) | Display metadata, default prompt, and Notion tool dependency |

## Scope

Designed for studying, synthesizing, and preserving learning material. Meeting notes, task tracking, and general Notion administration are outside its scope.

Results depend on the available source-reading tools and Notion connection. When a source or destination cannot be accessed, the skill reports that limitation and preserves a useful draft where possible.
