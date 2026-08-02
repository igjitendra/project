# Claude Code Skills Package

This archive is ready to extract into the root of a Git repository.

## Included skills

1. commit-writer
2. pr-reviewer
3. test-generator
4. dead-code-sweeper
5. refactor-bot
6. screenshot-localizer
7. docs-updater
8. dep-upgrader
9. bug-reproducer
10. release-notes

## Install in Termux

From your repository root:

```bash
unzip claude-code-skills.zip

git add .claude SKILLS-README.md
git commit -m "feat(tooling): add Claude Code skills"
git push origin main
```

If files already exist, review them before choosing whether to overwrite.
