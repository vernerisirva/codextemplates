# Plan Mode Trigger Rules

Purpose: use Plan Mode only when planning is likely to prevent rework, scope drift, or an expensive mistake.

Plan Mode and reasoning depth are separate choices. Plan Mode decides whether to clarify and sequence work before implementation; reasoning depth decides how much analysis the task needs.

## Use Plan Mode

Use Plan Mode when the user explicitly requests it, or when either condition is true:

- One high-risk trigger applies.
- Two or more ordinary triggers apply.

High-risk triggers:

- A wrong choice could cause data loss, security exposure, broken migrations, billing errors, privacy issues, or production downtime.
- The task changes architecture, public APIs, persistent data, authentication, deployment, or another hard-to-reverse boundary.
- The intended outcome is unclear enough that implementation could solve the wrong problem.

Ordinary triggers:

- The task spans multiple files, packages, services, or ownership boundaries.
- Several plausible approaches have meaningful trade-offs.
- Important constraints, acceptance criteria, or validation steps are missing.
- The task is difficult to describe and would benefit from focused questions.
- Investigation must happen before the implementation path is knowable.
- The work has several dependent stages that should be validated separately.

## Skip Plan Mode

Work directly when the task is:

- One obvious, reversible edit in a known file.
- A straightforward explanation, lookup, or read-only inspection.
- A mechanical change with an exact command and clear validation.
- A small bug fix with a reproduced cause and narrow regression test.
- Already specified with clear scope, constraints, done-when criteria, and implementation steps.

Do not use Plan Mode merely because a task mentions several files. Use it when those files create uncertainty, sequencing, risk, or a real design choice.

## Minimum Useful Plan

Keep the plan proportional. Capture only:

1. Goal and current context.
2. Constraints and out-of-scope work.
3. Key decision or unresolved question.
4. Implementation steps with affected areas.
5. Validation and done-when criteria.

Ask only questions whose answers could materially change the plan.

## Exit Rule

Leave Plan Mode and begin implementation when:

- The goal and scope are unambiguous.
- The important constraints and risks are named.
- The implementation path is concrete enough to act on.
- The validation command or manual check is known.
- No unresolved question could materially change the first step.

If planning is not reducing uncertainty, stop expanding the plan and take the smallest safe, verifiable action.

## Quick Decision

```text
Explicit request or one high-risk trigger? -> Use Plan Mode.
Two or more ordinary triggers?             -> Use Plan Mode.
Otherwise                                  -> Work directly and validate.
```

Official guidance reviewed: 2026-07-22. Codex recommends planning first for complex, ambiguous, or hard-to-describe tasks and supports toggling Plan Mode with `/plan` or Shift+Tab.
