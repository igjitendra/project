---
name: dep-upgrader
description: Upgrade project dependencies safely in small batches with compatibility checks, migrations, tests, and rollback on failure.
---

# Dependency Upgrader

## Goal

Apply justified dependency upgrades without silently breaking the project.

## Workflow

1. Detect the package manager and honor the existing lockfile.
2. Record the current version, requested target, runtime constraints, peer dependencies, and platform constraints.
3. Read available release notes, migration guidance, and breaking changes when they are accessible. If they are not accessible, state that limitation.
4. Upgrade one dependency at a time, except for packages that must remain version-aligned.
5. Apply only required migration changes. Do not mix unrelated refactors.
6. Run the relevant install, typecheck, lint, tests, build, and platform checks.
7. Inspect the lockfile diff for unexpected package churn.
8. If verification fails, diagnose it; roll back the attempted upgrade unless the user asks to keep the failing state for investigation.
9. Commit only after the user approves committing.

## Rules

- Never delete or regenerate a lockfile casually.
- Do not bypass peer-dependency or engine errors with force flags unless the user explicitly accepts the risk.
- Separate major upgrades when possible.
- Prioritize security fixes, but still verify compatibility.
- Never claim compatibility without running applicable checks.
- Do not expose registry tokens or environment secrets.

## Output

For each package, report old and new versions, migration changes, verification commands, result, and rollback status if applicable.
