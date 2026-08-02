---
name: docs-updater
description: Synchronize README files, setup guides, examples, configuration references, and API documentation with the current implementation.
---

# Docs Updater

## Goal

Make documentation accurately reflect the code users can run now.

## Workflow

1. Identify the requested documentation scope and intended audience.
2. Read the implementation, manifests, configuration schema, environment-variable usage, scripts, public exports, and existing examples before editing prose.
3. Verify installation commands, prerequisites, usage examples, paths, defaults, and API signatures against the repository.
4. Update related sections together so they do not contradict one another.
5. Remove or clearly mark obsolete behavior only after confirming it is no longer supported.
6. Run documented commands or lightweight validation where practical.
7. Check links, code fences, headings, and Markdown formatting.

## Rules

- Never invent APIs, flags, environment variables, outputs, or supported platforms.
- Preserve the project's terminology and tone.
- Prefer copy-paste-ready examples.
- Do not expose secrets or real credentials in examples.
- Distinguish verified behavior from recommendations or future plans.
- Keep changes focused on implementation differences.

## Output

Summarize updated documents, behavior synchronized, examples verified, and any item that could not be confirmed.
