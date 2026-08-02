---
name: dead-code-sweeper
description: Find and safely remove unreachable exports, orphan files, obsolete blocks, and unused dependencies while keeping builds and tests passing.
---

# Dead-Code Sweeper

## Goal

Reduce dead code without deleting dynamic, side-effectful, generated, or public API code.

## Workflow

1. Read project manifests and identify every runtime, test, script, native, and package entry point.
2. Build an import and usage map using repository search plus available compiler or linter diagnostics.
3. Classify candidates separately:
   - unused local symbols
   - unreferenced exports
   - orphan files
   - obsolete commented-out code
   - unused dependencies
4. For each candidate, check dynamic imports, reflection, route/file conventions, config references, native registration, side effects, code generation, and published APIs.
5. Present evidence and a deletion plan before destructive edits unless the user already approved the exact scope.
6. Remove one category or small coherent batch at a time.
7. Run the relevant typecheck, build, lint, and tests after each batch.
8. Revert the batch if verification fails and report why.

## Rules

- Never assume that "no static import" means unused.
- Exclude generated files, migrations, fixtures, scripts, native entry points, plugin files, and framework-convention files unless proven unused.
- Preserve package exports and public APIs unless the user explicitly approves a breaking change.
- Do not combine dead-code removal with unrelated refactoring.
- Never claim a size or performance improvement without measuring it.

## Output

Report confirmed removals, retained false positives, verification commands, and results.
