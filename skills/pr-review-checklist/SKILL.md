---
name: pr-review-checklist
description: Review pull requests and code changes for correctness, tests, security, performance, maintainability, scope creep, and release risk. Use when the user asks for a PR review, code review, diff audit, pre-merge check, regression assessment, or final risk summary before merging.
---

# PR Review Checklist

Review the change as a risk assessment. Prioritize defects and regressions over summaries, style preferences, or praise.

## Establish Scope

1. Read repository instructions and the narrowest relevant context files.
2. Identify the base and head of the review; inspect the complete diff.
3. Determine the intended behavior from the PR description, issue, tests, or changed documentation.
4. Map changed code to affected callers, interfaces, data flows, and tests.
5. Note any part of the requested review that cannot be inspected or validated.

Do not modify code unless the user explicitly asks for fixes.

## Review Categories

### Correctness

- Trace normal, boundary, error, and state-transition paths.
- Check assumptions about nullability, ordering, retries, concurrency, time, and partial failure.
- Look for broken callers, contracts, migrations, compatibility, and user-visible behavior.
- Confirm that the implementation matches the stated intent rather than merely passing existing tests.

### Tests

- Check that changed behavior has focused coverage, including meaningful failure and edge cases.
- Verify that assertions would fail for the suspected regression.
- Identify brittle, misleading, nondeterministic, or missing tests.
- Run the narrowest relevant validation commands when the environment permits.

### Security

- Inspect trust boundaries, authorization, validation, escaping, secrets, and sensitive data handling.
- Check injection, path traversal, unsafe deserialization, privilege escalation, and information disclosure where relevant.
- Avoid speculative security findings; state the concrete attack or failure path.

### Performance

- Inspect changed hot paths, loops, queries, network calls, allocations, caching, and payload sizes.
- Flag only regressions with a plausible workload and material impact.
- Distinguish measured evidence from reasoned risk.

### Maintainability

- Check whether the change creates duplicated policy, hidden coupling, unclear ownership, or difficult failure modes.
- Prefer findings that increase defect risk or operational burden.
- Do not report personal style preferences already handled by formatters or linters.

### Scope Creep

- Compare the diff with the stated objective.
- Identify unrelated behavior changes, broad refactors, generated churn, or new dependencies that increase review risk.
- Treat necessary supporting changes as in scope when their connection is clear.

## Finding Standard

Report a finding only when all of these are available:

- A specific defect or credible regression introduced by the change.
- Evidence in the diff or directly affected code.
- A realistic trigger or execution path.
- A concrete impact.
- A narrow remediation direction.

Use these priorities:

- `P0`: immediate, widespread catastrophic impact; block release.
- `P1`: serious correctness, security, or data-loss risk; block merge.
- `P2`: material defect affecting a realistic case; fix before or soon after merge.
- `P3`: low-impact issue worth addressing; do not use for optional polish.

Attach each finding to the smallest useful file and line range. Keep one root cause per finding. Do not inflate severity because an area is generally sensitive.

## Validate Findings

1. Re-read the relevant pre-change and post-change path.
2. Search for safeguards, callers, tests, or invariants that could disprove the finding.
3. Run a focused test or static check when practical.
4. Remove findings that remain hypothetical or depend on unstated assumptions.
5. Record validation commands and their outcomes.

## Output

Lead with findings ordered by priority. For each finding provide:

- Priority and concise title.
- File and line reference.
- Trigger and impact.
- Evidence and remediation direction.

Then provide:

- Open questions or assumptions that materially affect the review.
- Validation performed and any gaps.
- Final risk summary: overall risk, merge recommendation, and the main residual risk.

If no actionable findings remain, say so clearly. Still report validation gaps and residual risk; do not invent findings to fill categories.

## Stop Conditions

Stop and report the limitation when:

- The diff, base revision, or required generated artifact is unavailable.
- Validation needs credentials, production access, destructive actions, or user approval.
- Repository state prevents distinguishing the PR from unrelated local changes.
- The intended behavior is ambiguous enough to change whether a finding is valid.

State the smallest missing input or next check needed to continue.
