# Long-Running Codex Goal Workflow

Purpose: keep Codex oriented during long tasks by anchoring the work to one persistent goal, small checkpoints, explicit validation, and a clean resume trail.

Use this when a task may take more than one short Codex turn, touches several files, or requires investigation before implementation.

Source inspiration: a public post by Gabriel Chua about Codex working for long stretches when a persistent `/goal` is set, while the hard part is staying oriented during the run.

## 1. Goal Setup

Use `/goal` when the Codex surface supports it. Otherwise, paste the goal at the top of the thread.

```text
Goal:
[one concrete outcome]

Why it matters:
[short reason]

Scope:
[files, folders, issue, feature, or repo area]

Out of scope:
[what Codex should not change]

Done when:
[observable finish condition]
```

Good goals are specific enough that Codex can decide whether new work is helping or distracting.

## 2. Orientation Packet

Before asking Codex to work for a long stretch, provide or ask it to read:

- `AGENTS.md`
- `docs/agent-context/validation.md`
- `docs/agent-context/architecture-map.md` when present
- the relevant issue, task, bug report, design note, or failing command
- the smallest set of files likely to matter

Ask Codex to summarize only:

- current goal
- repo rules that affect this task
- likely files to inspect first
- narrowest validation command
- first checkpoint

## 3. Checkpoint Plan

Ask Codex to divide the work into checkpoints that can each be validated.

```text
Checkpoint 1:
[investigation or first small change]
Validation:
[command or readback]

Checkpoint 2:
[next small change]
Validation:
[command or readback]

Checkpoint 3:
[final integration or cleanup]
Validation:
[command or readback]
```

Each checkpoint should leave the repo in an understandable state.

## 4. Work Rules

Tell Codex:

- Keep the goal visible in status updates.
- Re-read the goal before changing direction.
- Prefer the narrowest useful file reads.
- Do not broaden scope without naming why.
- Validate after each meaningful checkpoint.
- Stop and ask when the next action needs credentials, destructive commands, production data, or a scope change.
- Leave unrelated files untouched.

## 5. Orientation Check Prompt

Use this when Codex has been working for a while.

```text
Pause for orientation.

Restate:
- current goal
- what is done
- what remains
- files changed
- validation already run
- next checkpoint
- risks or unknowns

Then continue only if the next step still serves the goal.
```

## 6. Drift Check

Use this when the task starts expanding.

```text
Before continuing, compare the next proposed action to the original goal.

Classify it as:
- required for the goal
- useful but optional
- unrelated scope creep

If it is optional or unrelated, stop and ask before doing it.
```

## 7. Validation Gate

Before final response, require:

- readback or inspection of changed files
- task-specific validation from `docs/agent-context/validation.md`
- `git diff --check` for text changes
- tests, lint, build, or manual check when relevant
- explicit note for anything not validated

Codex should not claim the task is complete until the validation gate is satisfied.

## 8. Handoff Or Resume Note

If the task is paused, compacted, or continued later, leave:

```text
Goal:
[same goal]

Current state:
[what is done and what is not]

Files changed:
[paths]

Validation run:
[commands and results]

Next checkpoint:
[one concrete next action]

Risks:
[known unknowns or blocked items]
```

## 9. After-Action Review

For serious tasks, capture one lesson:

- Did the persistent goal reduce drift?
- Did Codex read the right files?
- Did checkpoint validation catch anything?
- Was the task too large for one goal?
- What should become a reusable prompt, checklist, or context-file update?

Store the lesson in the project’s review, prompt, checklist, or `AGENTS.md` system rather than only in chat.
