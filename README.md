# Codex Templates

Reusable templates for starting and maintaining Codex-friendly repositories.

## Templates

- `templates/repo-level-AGENTS.md` - a repo-level `AGENTS.md` template with repo map, commands, working rules, coding style, testing expectations, and done-when criteria.
- `docs/agent-context/architecture-map.md` - a smallest-useful architecture map template for Codex context.
- `docs/agent-context/validation.md` - a validation command map template for install, typecheck, lint, test, package-specific commands, and done-when criteria.
- `docs/agent-context/current-research.md` - a freshness-controlled template for time-sensitive research and its project impact.
- `workflows/research-budget.md` - a bounded research workflow that starts with official sources and stops when the implementation decision is supported.
- `workflows/long-running-codex-goal.md` - a workflow for keeping long Codex tasks oriented around a persistent goal, checkpoints, validation, and handoff.
- `profiles/plan-mode-trigger-rules.md` - rules for using Plan Mode only when ambiguity, risk, or task structure justifies planning first.
- `prompts/plan-mode.md` - a read-only Plan Mode prompt for identifying the smallest file set, implementation path, risks, validation, and approval gate.
- `checklists/mcp-tool-audit.md` - a reusable audit for keeping MCP servers, plugins, and connectors useful without speculative tool usage.
- `skills/pr-review-checklist/` - a reusable skill for evidence-backed PR reviews across correctness, tests, security, performance, maintainability, and scope.
- `skills/test-writer/` - a reusable skill for focused tests, regression coverage, and validation of changed behavior.
- `guides/codex_session_audit_guide.md` - editable source for the weekly Codex session audit guide.
- `output/pdf/codex_session_audit_guide.pdf` - printable weekly Codex session audit guide.

## How To Use

1. Copy the template into a repository as `AGENTS.md`.
2. Replace bracketed prompts with project-specific details.
3. Keep the file short enough that Codex can read it at the start of a session.
4. Update it whenever repeated guidance shows up in chat.
