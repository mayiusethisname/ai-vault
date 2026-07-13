---
name: design-before-coding
description: Use when starting a new feature, app, workflow, component, automation, or behavior change before implementation. Helps Codex clarify intent, scope, constraints, user workflow, architecture, and acceptance criteria before writing code or files.
---

# Design Before Coding

Start by understanding the work before implementing it. Use this skill when the request is more than a trivial command or when assumptions could change the result.

## Workflow

1. Inspect the current project context first: files, docs, package metadata, tests, and existing patterns.
2. Restate the goal in concrete terms.
3. Identify missing decisions that would materially change implementation.
4. Ask only necessary questions. Prefer one question at a time unless the user explicitly asked for a plan.
5. Propose 2-3 approaches when there is a real tradeoff.
6. State the recommended approach and why.
7. Define acceptance criteria before editing files.

## Keep It Lightweight

For small tasks, the design can be 3-5 bullets. Do not turn every request into a long ceremony.

## Output Shape

Use this compact format when useful:

```md
Goal:
Constraints:
Assumptions:
Approach:
Acceptance criteria:
```

## Red Flags

Pause before implementation if:

- The user asks for a broad app/platform without choosing a first slice.
- Multiple independent subsystems are mixed together.
- Success criteria are vague.
- Data ownership, auth, deployment, or destructive behavior is unclear.
- The request conflicts with existing project patterns.

## Handoff

After design is clear, proceed to implementation or use a planning skill if the work has multiple dependent steps.
