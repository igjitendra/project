---
name: pr-reviewer
description: Review code changes for correctness, security, data loss, regressions, and performance risks. Use before opening or merging a pull request.
---

# PR Reviewer

## Goal

Find actionable defects in the proposed changes while avoiding low-value style noise.

## Workflow

1. Determine the review range. Prefer the user-provided base branch or commit; otherwise inspect repository status and available branches before choosing.
2. Read the complete diff and the full context of every changed file.
3. Inspect relevant callers, types, tests, configuration, and platform-specific code when needed to validate a finding.
4. Check for:
   - incorrect logic and unhandled edge cases
   - security or privacy vulnerabilities
   - data loss, corruption, and unsafe migrations
   - concurrency, async, and lifecycle defects
   - broken error handling or resource cleanup
   - performance regressions on meaningful paths
   - React Native or Expo platform incompatibilities
   - missing tests for changed high-risk behavior
5. Run focused tests or static checks when available and safe.
6. Report only findings supported by evidence from the code.

## Severity

- **Critical:** exploitable security issue, widespread data loss, or production outage risk.
- **High:** likely user-facing failure, serious regression, or major security weakness.
- **Medium:** real defect with limited impact or a meaningful maintainability risk that can cause failures.

## Rules

- Skip formatting preferences and minor style nits.
- Do not invent defects to fill the report.
- Every finding must include the location, cause, impact, and a concrete fix.
- Keep summaries concise and prioritize the highest-risk findings.
- If no actionable defect is found, say `No issues found.`

## Output

```markdown
## Findings

### HIGH — Short title
`path/to/file.ts:42`

Cause and impact.

**Fix:** Specific corrective action.

## Verification
- Checks or tests run
```
