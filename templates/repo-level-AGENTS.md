# AGENTS.md

Purpose: help Codex work efficiently in this repository without re-learning project context every session.

## Project Summary

- Product/domain: [what this repository is for]
- Primary users: [who uses the software or artifacts]
- Current priority: [the main thing Codex should optimize for right now]
- Risk level: [low, medium, high; explain if high]

## Repo Map

- `src/` - [main application or package code]
- `tests/` - [automated tests]
- `docs/` - [project documentation]
- `scripts/` - [developer scripts and one-off utilities]
- `config/` - [configuration files]
- `assets/` - [static assets, fixtures, or examples]

Add or remove entries so this map matches the real repository. Prefer exact paths over broad descriptions.

## Common Commands

Use the commands that actually work in this repo.

```bash
# install dependencies
[install command]

# run the app or local service
[dev command]

# run tests
[test command]

# run linting
[lint command]

# run formatting
[format command]

# build or package
[build command]
```

If a command is unavailable, remove it rather than leaving a stale placeholder.

## Working Rules

- Read this file and the relevant local files before making non-trivial changes.
- Prefer focused edits over broad rewrites.
- Do not change unrelated files to make a task look cleaner.
- Preserve user work in a dirty worktree; never revert changes you did not make unless explicitly asked.
- Ask before changing public APIs, data formats, migrations, security-sensitive code, or release behavior.
- Use the lowest reasoning depth that can pass validation.
- Record reusable lessons in this file or the nearest project documentation.

## Coding Style

- Follow existing patterns before introducing new abstractions.
- Keep names descriptive and consistent with nearby code.
- Keep functions and modules focused on one responsibility.
- Add comments only when they explain non-obvious intent, constraints, or trade-offs.
- Prefer structured parsers and framework utilities over ad hoc string manipulation.
- Keep formatting consistent with the repo's formatter.

## Testing Expectations

- Add or update tests when behavior changes.
- Run the narrowest test command that proves the change first.
- Run broader validation when touching shared behavior, public interfaces, or risky code.
- If tests cannot be run, state why and provide the best available manual validation.
- Do not claim work is complete until validation has been run and checked.

## Done-When Criteria

A task is done when:

- The requested behavior or artifact exists.
- Relevant files have been read back or inspected.
- Tests, lint, build, or manual validation have passed.
- Edge cases from the request have been considered.
- The final response names what changed and how it was validated.

## Handoff Notes

When stopping mid-task, leave:

- Current goal.
- Files changed.
- Commands already run and their results.
- Known blockers or uncertainties.
- Recommended next step.
