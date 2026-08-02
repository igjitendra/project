---
name: release-notes
description: Generate concise, user-facing Markdown release notes from a verified Git range, grouping related changes and highlighting breaking changes.
---

# Release Notes

## Goal

Convert repository history into accurate release notes that users can understand.

## Workflow

1. Confirm the release version and Git range, such as `previous-tag..current-tag`.
2. Read commits in that range and inspect relevant diffs or pull requests when commit messages are ambiguous.
3. Exclude merges, reverts, internal refactors, tests, and maintenance unless they affect users or release operations.
4. Group related work into:
   - New features
   - Improvements
   - Fixes
   - Documentation
   - Security
   - Breaking changes
5. Merge duplicate commits describing the same user-facing change.
6. Rewrite technical language into concise outcome-focused language without inventing impact.
7. Include migration instructions only when verified from the code or provided documentation.
8. Check that every listed item belongs to the selected range.

## Rules

- Do not invent issue numbers, contributors, dates, metrics, or features.
- Do not expose sensitive security details before disclosure is approved.
- Highlight breaking changes and required user action prominently.
- Keep implementation details only when users need them.
- Produce clean Markdown suitable for GitHub Releases.

## Output

```markdown
# Release vX.Y.Z

## New features
- User-facing outcome

## Fixes
- Corrected user-facing problem

## Breaking changes
- Required migration action
```
