# Codex Session Audit Guide

Use this once per week to improve how you work with Codex. The goal is not to judge every session perfectly; the goal is to notice patterns and make one concrete upgrade.

## Weekly Setup

- Review 3-5 meaningful Codex sessions from the week.
- Pick sessions that had real work, not only quick questions.
- Collect the prompt, outcome, validation, corrections, and any reusable artifacts created.
- Spend 20-30 minutes total.

## Scorecard

Score each category from 1 to 5.

| Category | Question | Score |
| --- | --- | --- |
| Goal clarity | Was the desired outcome clear before Codex started? | 1-5 |
| Context quality | Did Codex get the right files, constraints, and background? | 1-5 |
| Reasoning fit | Was the mode low enough to be efficient but strong enough to pass validation? | 1-5 |
| Tool discipline | Did Codex inspect, edit, test, and verify in the right order? | 1-5 |
| Corrections | How many user corrections were needed? Lower is better. | 1-5 |
| Reuse | Did the session create or improve a reusable artifact? | 1-5 |
| Validation | Was done proven by a command, readback, screenshot, or manual check? | 1-5 |

## Evidence To Capture

For each reviewed session, write:

- Task name.
- Reasoning/profile level used.
- Files Codex inspected.
- Files Codex changed.
- Validation command or check.
- Number of corrections.
- What wasted tokens.
- What should become a reusable prompt, checklist, template, or `AGENTS.md` rule.

## Pattern Questions

- Where did Codex ask for context that could have been in a file?
- Where did Codex inspect too much or too little?
- Which prompts were longer than necessary?
- Which tasks should have used a lower reasoning mode?
- Which tasks should have escalated sooner?
- Which mistakes happened more than once?
- Which reusable artifact would prevent the same explanation next week?

## Weekly Decision

Choose exactly one improvement:

- Update `AGENTS.md`.
- Add or refine a prompt.
- Add or refine a checklist.
- Add or refine a template.
- Add a rule to the reasoning profile guide.
- Remove outdated context that made Codex slower.

## Output Template

```text
Week:
Sessions reviewed:
Average score:
Best session:
Most wasteful session:
Main pattern:
One improvement:
File to update:
Validation for next week:
```

## Done When

The audit is done when:

- At least 3 sessions were reviewed.
- One repeated pattern was named.
- One artifact was created or improved.
- The next week has a specific validation check.
