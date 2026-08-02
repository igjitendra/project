---
name: bug-reproducer
description: Reproduce a reported bug, reduce it to a minimal failing case, identify the root cause, and verify a proposed fix.
---

# Bug Reproducer

## Goal

Turn an uncertain bug report into a deterministic reproduction and evidence-based root cause.

## Workflow

1. Capture expected behavior, actual behavior, exact steps, environment, version, frequency, and available logs.
2. Reproduce the issue without modifying production code.
3. Change one variable at a time and reduce the case to the smallest deterministic example.
4. Add a focused failing test or reproducible script when practical.
5. Trace the failing path using logs, debugger output, call sites, state transitions, and recent relevant changes.
6. Separate the root cause from downstream symptoms.
7. Propose the smallest safe fix.
8. Verify the fix against the minimal reproduction, regression tests, and nearby edge cases.
9. Keep the regression test whenever it provides durable protection.

## Rules

- Do not guess a root cause before reproducing or collecting sufficient evidence.
- Do not weaken assertions or suppress errors to make the symptom disappear.
- Do not combine unrelated cleanup with the fix.
- Record environmental limitations when exact reproduction is impossible.
- Distinguish confirmed facts, hypotheses, and unverified assumptions.

## Output

Provide reproduction steps, minimal failing case, root cause with evidence, proposed or applied fix, and final verification results.
