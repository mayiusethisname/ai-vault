---
name: docx-review
description: Use when creating, reading, editing, reviewing, redlining, commenting on, or converting Word documents and .docx files. Applies to memos, reports, letters, templates, tracked changes, comments, formatting preservation, and polished document deliverables.
---

# DOCX Review

Handle Word documents carefully. A `.docx` file is a ZIP of XML files, and small structural mistakes can corrupt the document.

## Workflow

1. Identify whether the task is reading, creating, editing, redlining, commenting, or converting.
2. For reading, extract text with a document-aware tool and preserve headings, tables, comments, and tracked changes if relevant.
3. For new documents, generate structured content with real headings, lists, tables, headers, and footers rather than plain text pretending to be a document.
4. For edits, preserve existing formatting and make the smallest necessary change.
5. For tracked changes or comments, use proper Word constructs rather than inline annotations in body text.
6. Render or convert the final document for visual QA when layout matters.

## Editing Principles

- Preserve the user's template and style conventions.
- Do not flatten lists, tables, footnotes, or comments unless requested.
- Keep changes minimal and reviewable.
- For legal or contract-style documents, preserve numbering and cross-references.
- Validate the document opens after modification.

## Common Pitfalls

- Replacing the whole document for a small edit.
- Breaking numbering by manually typing numbers.
- Losing tracked changes or comments during conversion.
- Using visual bullets instead of real list structures.
- Assuming extracted plain text is enough for formatting-sensitive tasks.

## Output

When reporting work, mention the file changed, the type of edit made, and any layout or validation checks performed.
