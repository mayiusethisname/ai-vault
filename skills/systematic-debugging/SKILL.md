---
name: systematic-debugging
description: Use when facing a bug, failing test, build error, runtime error, flaky behavior, performance issue, integration failure, or unexpected output before proposing fixes. Guides Codex to find evidence and root cause first.
---

# Systematic Debugging

Do not guess at fixes. Find the failure point, prove the cause, then make the smallest correction.

## Workflow

1. Read the full error message, stack trace, logs, and failing command output.
2. Reproduce the failure with the smallest reliable command or scenario.
3. Check recent changes and nearby code paths.
4. Compare broken behavior with a working example in the same codebase.
5. Form one hypothesis at a time: `I think X causes Y because Z`.
6. Test the hypothesis with the smallest probe or diagnostic change.
7. Only after the cause is supported, implement the fix.
8. Verify the original failure no longer occurs and no related tests regressed.

## Multi-Layer Systems

When the bug crosses boundaries, add evidence at each boundary before fixing:

- input received
- output returned
- config/env visible at that layer
- external API response or file state
- assumptions about timing, auth, permissions, or paths

## Fix Rules

- Fix root cause, not symptoms.
- Change one thing at a time.
- Do not bundle cleanup unless it is necessary to expose or fix the cause.
- For bugs, add or update a regression test where practical.

## Red Flags

Stop and return to evidence gathering if you catch yourself saying:

- "It's probably..."
- "Let's just try..."
- "This should fix it" without a reproduction.
- "I'll test after the fix."
- More than two fixes have failed.

After three failed fixes, question the architecture or initial assumptions before trying another patch.
