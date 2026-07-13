---
name: tdd-workflow
description: Use when implementing a feature, bug fix, refactor, or behavior change where tests can reasonably be added. Guides Codex through red-green-refactor with minimal tests, minimal implementation, and verification.
---

# TDD Workflow

Use tests to define behavior before implementation when the project has or can support tests.

## Cycle

1. Pick one behavior.
2. Write the smallest failing test for that behavior.
3. Run only the relevant test and confirm it fails for the expected reason.
4. Write the smallest implementation that makes it pass.
5. Run the focused test again.
6. Run the relevant broader test set.
7. Refactor only after tests are green.
8. Repeat for the next behavior.

## Good Test Shape

A good test:

- names the behavior clearly
- asserts externally visible behavior
- avoids testing implementation details unless unavoidable
- uses real code paths where practical
- covers one behavior at a time

## When Tests Are Hard

If the test is difficult to write, inspect the design. Hard-to-test code often means unclear boundaries, hidden state, or tight coupling. Prefer improving the interface over adding fragile mocks.

## Exceptions

Ask before skipping tests for:

- throwaway prototypes
- pure configuration changes
- generated files
- visual-only changes with no test harness

If tests are impossible or not worth it, state why and use another verification method such as a focused script, manual reproduction, screenshot, or build command.
