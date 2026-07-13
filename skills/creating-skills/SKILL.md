---
name: creating-skills
description: Use when creating, updating, reviewing, or organizing reusable AI skills for Codex, ChatGPT, Claude, or an ai-vault repository. Applies to SKILL.md structure, trigger descriptions, reference files, scripts, and deciding whether a workflow deserves a skill.
---

# Creating Skills

Create a skill only when it captures a repeatable workflow, non-obvious procedure, domain reference, or tool pattern that future AI sessions should reuse.

## Decide Whether It Deserves a Skill

Create a skill when:

- the workflow will recur
- the steps are easy to forget or get wrong
- the task depends on specific tools, formats, or conventions
- examples or references would save future context
- the trigger condition is clear

Do not create a skill for:

- one-off notes
- generic advice the model already knows
- project-specific instructions better kept in `AGENTS.md`
- huge copied documentation with no workflow guidance

## Structure

Use this folder shape:

```text
skills/<skill-name>/
  SKILL.md
  references/   # optional
  scripts/      # optional
  assets/       # optional
```

Keep `SKILL.md` concise. Move long details into `references/` and tell the agent when to read them.

## Frontmatter

Use only required fields unless the target runtime needs more:

```yaml
---
name: skill-name
description: Use when ...
---
```

The description is the trigger. It should say when to use the skill, including concrete phrases, file types, tasks, and contexts.

## Body

A useful skill body usually includes:

- the core principle
- a short workflow
- tool selection rules
- output format expectations
- common pitfalls
- validation checks

## Quality Checks

Before saving:

- Name is lowercase hyphen-case.
- Description is specific enough to trigger correctly.
- The skill is not just a copied README.
- Instructions are actionable.
- Long references are split out.
- The skill says how to verify the work.

## Iteration

After using a skill, update it if the agent struggled, skipped a step, used the wrong tool, over-produced, or missed an important validation check.
