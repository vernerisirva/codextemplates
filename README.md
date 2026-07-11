# Codex Templates

Reusable templates for starting and maintaining Codex-friendly repositories.

## Templates

- `templates/repo-level-AGENTS.md` - a repo-level `AGENTS.md` template with repo map, commands, working rules, coding style, testing expectations, and done-when criteria.
- `docs/agent-context/architecture-map.md` - a smallest-useful architecture map template for Codex context.
- `docs/agent-context/validation.md` - a validation command map template for install, typecheck, lint, test, package-specific commands, and done-when criteria.
- `workflows/long-running-codex-goal.md` - a workflow for keeping long Codex tasks oriented around a persistent goal, checkpoints, validation, and handoff.
- `skills/pr-review-checklist/` - a reusable skill for evidence-backed PR reviews across correctness, tests, security, performance, maintainability, and scope.
- `skills/test-writer/` - a reusable skill for focused tests, regression coverage, and validation of changed behavior.
- `guides/codex_session_audit_guide.md` - editable source for the weekly Codex session audit guide.
- `output/pdf/codex_session_audit_guide.pdf` - printable weekly Codex session audit guide.

## How To Use

1. Copy the template into a repository as `AGENTS.md`.
2. Replace bracketed prompts with project-specific details.
3. Keep the file short enough that Codex can read it at the start of a session.
4. Update it whenever repeated guidance shows up in chat.
