---
name: review-github-stars
description: Use when reviewing a user's GitHub Star list, newly starred repositories, or a pasted owner/repo list to decide what is reusable in an AI knowledge vault and what should become a local skill
---

# Review GitHub Stars

## Overview

Turn starred repositories into reusable decisions and working assets. Inspect evidence from the repository, judge practical reuse value, update the vault index, and create a skill only when the repository teaches a repeatable workflow rather than merely providing code or a README.

## Workflow

1. Establish the input and checkpoint.
   - Prefer the connected GitHub account's Star list.
   - If Stars are unavailable, use a Stars page or a single pasted batch of `owner/repo` identifiers.
   - Treat repositories already recorded in `starred-repos.md` as reviewed unless the user asks for a refresh.
   - If no checkpoint exists, state that the review is a full baseline review; do not invent a date.
   - Record the review date and the source of the list.

2. Inspect repositories in a batch.
   - Group the list before inspecting it; do not ask the user to provide repositories one at a time.
   - For each repository, prioritize `README.md`, `AGENTS.md`, `CLAUDE.md`, `SKILL.md`, prompt files, examples, configuration, package metadata, license, and recent activity.
   - Use repository contents and documentation as evidence. Do not rate a repository highly because it is popular.
   - Note missing documentation, stale commits, abandoned releases, unclear licensing, external data transfer, credentials, and destructive commands.

3. Classify by actual use.
   - Start with: AI prompts, Codex/development automation, documentation, legal/research, PDF/file processing, data analysis, learning/study, or other reference.
   - Add or change a category when the repository does not fit honestly.
   - Give each repository one disposition: `use-now`, `adapt`, `reference-only`, or `skip`.
   - `use-now` requires a concrete user situation and a plausible next action.
   - `adapt` means the workflow is valuable but needs compatibility, security, licensing, or maintenance review.
   - `reference-only` means the ideas are useful but the repository itself should not be installed or copied.
   - `skip` means the repository has low practical value or disproportionate risk; explain why.

4. Decide whether to create a skill.
   Create a skill only when all of these are true:
   - The repository contains a repeatable task or decision process.
   - The inputs and expected outputs can be described.
   - The workflow will recur across repositories or projects.
   - The skill adds more value than a short note or link.
   - It does not duplicate an existing skill.
   - Risky external actions can be gated by explicit confirmation.

   Do not create a skill for a one-off script, a generic library, a README summary, a project-specific convention, or code that should be installed unchanged. Preserve those as a reference or integration note.

5. Write the vault entry.
   For every reviewed repository, use this shape:

   ```markdown
   ### owner/repo
   - **Category:** ...
   - **Original link:** ...
   - **Core use:** ...
   - **Useful when:** ...
   - **Important files:** ...
   - **How to apply:** ...
   - **Cautions:** ...
   - **Maintenance/licensing note:** ...
   - **Disposition:** use-now | adapt | reference-only | skip
   - **Skill candidate:** yes/no, with one-sentence reason
   ```

   Keep the entry specific enough to support a later decision. Separate observed facts from inferences.

6. Update files safely.
   - Update `starred-repos.md` only after the review is complete.
   - Add new skill files only when the skill decision is yes.
   - Before changing a remote file, fetch its current contents and current blob SHA; do not overwrite based on a stale copy.
   - Do not install plugins, copy skills into local runtime directories, open PRs, or make unrelated repository changes unless the user explicitly asks.
   - If the GitHub connector cannot write, return the complete Markdown draft and list the exact files that remain to be written.

## Output Contract

Return, in this order:

1. A total Star-list summary: count, categories, and dispositions.
2. The immediately useful repositories with reasons.
3. The complete Markdown draft or the exact files updated.
4. Skill candidates with proposed paths and trigger descriptions.
5. Uncertainty and risk notes, including inaccessible repositories or unverified maintenance/licensing information.

## Quality Checks

Before finishing, verify:

- Every input repository appears exactly once or is explicitly marked inaccessible.
- New versus previously reviewed repositories is clear.
- Every recommendation has a concrete use case.
- Important files are named from repository evidence.
- Stale, abandoned, misleading, or low-value repositories are called out.
- No repository is converted into a skill solely because it is famous.
- No external write or installation is implied to have happened unless it actually did.
