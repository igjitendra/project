---
name: test-generator
description: Create and run meaningful tests for a target source file using the project's existing test stack. Use for unit, integration, component, async, and error-path coverage.
---

# Test Generator

## Goal

Add maintainable tests that verify observable behavior and pass with the project's existing test setup.

## Workflow

1. Read the target file, its callers, types, and the nearest existing tests.
2. Detect the current test runner, assertion library, naming conventions, setup files, and commands from project configuration.
3. Identify the target's public behavior and risk areas.
4. Create tests for relevant cases:
   - normal or happy path
   - boundary values and empty input
   - invalid input and thrown errors
   - async resolution, rejection, cancellation, or timeout behavior
   - state transitions and cleanup
   - React Native rendering and user interaction when applicable
   - platform-specific Expo behavior when applicable
5. Mock only external boundaries such as network, filesystem, clock, notifications, or storage. Do not mock the unit being tested.
6. Run the smallest relevant test command.
7. Fix test defects and rerun until green. If the product code appears defective, report the failing behavior instead of weakening the assertion.

## Rules

- Match the existing project style.
- Add no dependency unless the user approves it.
- Prefer behavior-based assertions over implementation details or snapshots.
- Keep tests deterministic and independent.
- Never claim coverage or passing status without running the relevant command.
- Do not modify production behavior merely to make a test pass unless the user requests the fix.

## Output

Summarize created or updated test files, cases covered, the command run, and the result.
