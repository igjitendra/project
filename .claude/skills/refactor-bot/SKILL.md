---
name: refactor-bot
description: Refactor one focused area while preserving observable behavior and public APIs. Use to split large files, extract responsibilities, or simplify structure safely.
---

# Refactor Bot

## Goal

Improve structure without changing user-visible behavior.

## Workflow

1. Select one file or one tightly scoped responsibility per run.
2. Read its callers, exports, tests, types, and side effects.
3. Run existing focused tests before editing to establish a baseline.
4. Map responsibilities and propose extraction boundaries.
5. Preserve public exports, function signatures, error behavior, ordering, state transitions, and side effects.
6. Move code in small steps. Avoid drive-by fixes, renames, formatting churn, and dependency upgrades.
7. Run typecheck, focused tests, and relevant build checks after the refactor.
8. Compare the final diff with the original behavior contract.

## Rules

- Refactor and behavior change belong in separate work.
- Do not batch unrelated files.
- Do not alter public APIs without explicit approval.
- Prefer clear modules over excessive abstraction.
- Do not claim behavior preservation unless verification passes.
- If baseline tests already fail, record that before changing code.

## Output

Summarize extracted responsibilities, preserved API surface, files changed, and verification results.
