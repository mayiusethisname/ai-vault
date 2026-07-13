---
name: plan-writing
description: Use when a task has multiple dependent implementation steps, touches several files, needs staged verification, or should be handed to Codex/subagents later. Produces practical implementation plans with files, order, tests, and acceptance checks.
---

# Plan Writing

Create plans that another coding agent can execute without rediscovering the whole problem.

## Before Writing the Plan

1. Confirm the goal and acceptance criteria.
2. Inspect relevant files and existing patterns.
3. Identify the smallest useful implementation slice.
4. List files likely to be created or modified.
5. Decide what tests or checks prove success.

## Plan Format

Use this structure:

```md
# <Feature> Implementation Plan

Goal:
Approach:
Files:
Verification:

## Tasks

### Task 1: <name>
Files:
Steps:
Checks:

### Task 2: <name>
Files:
Steps:
Checks:
```

## Task Quality

Each task should:

- have a concrete output
- be independently reviewable
- name exact files when known
- include verification commands or manual checks
- avoid vague placeholders like `handle edge cases`

## Scope Control

Split the plan if it contains independent systems such as auth, billing, chat, analytics, deployment, and admin tools. A good plan should produce working software incrementally.

## Execution Notes

When executing the plan yourself, keep the checklist updated and verify after each meaningful task rather than waiting until the end.
