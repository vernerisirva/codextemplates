---
name: test-writer
description: Design and add focused automated tests for changed behavior, regressions, edge cases, and failure paths. Use when Codex needs to write tests, improve coverage for a code change, add a regression test, or decide what validation is sufficient before completion.
---

# Test Writer

Turn a behavior change into a small, meaningful test plan and implementation. Prefer tests that protect user-visible or contract-level behavior over tests coupled to internal implementation details.

## Establish Context

1. Read repository instructions and the narrowest validation guidance.
2. Inspect the changed code, its callers, and nearby tests before writing anything.
3. Identify the intended behavior from the task, issue, documentation, or existing contract.
4. Find the repository's test runner, test layout, fixtures, factories, and naming conventions.
5. Check whether the behavior is already covered; extend an existing test when that is clearer than adding a new file.

If the expected behavior or test command cannot be determined and the uncertainty changes the test design, ask one focused question.

## Build the Test Matrix

Cover only cases that matter for the change:

- Happy path: the primary supported behavior.
- Boundaries: empty, minimum, maximum, missing, duplicate, malformed, or expired inputs as relevant.
- Failure path: expected errors, rejected operations, timeouts, retries, and partial failure.
- Regression path: the smallest input that would have failed before the fix.
- Integration path: affected boundaries between modules, storage, network, UI, or external services.

Do not force every category into every test. Avoid broad snapshot churn and tests that merely restate implementation structure.

## Implement

1. Choose the smallest test level that can prove the behavior: unit, component, integration, or end-to-end.
2. Reuse existing fixtures and helpers when they keep the test readable and deterministic.
3. Arrange only the state needed for the scenario.
4. Assert the observable result, important side effects, and meaningful error details.
5. Keep each test focused on one behavior and give it a failure-explaining name.
6. Avoid sleeps, real external services, shared mutable state, random data without a seed, and assertions on incidental formatting.

Do not weaken production behavior, remove an assertion, or change test configuration just to make a test pass. If a test exposes a product defect, report it or fix it only when the user requested implementation work.

## Validate

Run validation in this order:

1. The new or directly affected test.
2. The surrounding test file or package.
3. Typecheck, lint, build, or integration checks required by the repository.
4. Broader checks only when the change crosses boundaries or the project requires them.

When a command fails, distinguish a test failure from an environment or pre-existing failure. Inspect the output before changing the test.

## Done When

The task is complete when:

- The test expresses the intended behavior and would fail for the relevant regression.
- Important boundary and failure cases are covered or explicitly ruled out.
- The test is deterministic, readable, and consistent with local conventions.
- The narrowest relevant validation passes.
- Any broader validation gap, unrelated failure, or remaining risk is recorded.

## Output

Report briefly:

- Tests added or changed and the behavior each protects.
- Validation commands and results.
- Any cases intentionally not covered and why.
- Remaining risk or follow-up needed.

If no useful automated test can be added, explain the constraint and provide an exact manual validation procedure with expected results.
