# Architecture Map

Purpose: give Codex the smallest useful map of this repository before it makes design, debugging, or multi-file implementation decisions.

Keep this file short. Prefer exact paths and ownership boundaries over long explanations.

## System Summary

- Product/domain: [what this repo builds or supports]
- Primary runtime: [web app, API, CLI, worker, library, data pipeline, etc.]
- Main language/framework: [language and framework]
- Deployment target: [where this runs]
- Current architecture risk: [low, medium, high; explain briefly]

## Main Apps And Packages

| Path | Purpose | Owner/Boundary | Notes |
| --- | --- | --- | --- |
| `apps/[app-name]/` | [what this app does] | [team/module owner] | [runtime, entrypoint, or key constraint] |
| `packages/[package-name]/` | [what this package provides] | [who owns changes] | [public API or dependency notes] |
| `src/` | [main source area if this is a single-package repo] | [owner] | [important conventions] |

Remove rows that do not apply. Add only the paths Codex needs to navigate the repo safely.

## Ownership Boundaries

- [Boundary 1]: [what code belongs here, what code does not belong here]
- [Boundary 2]: [what code belongs here, what code does not belong here]
- Shared code rule: [when to create shared code vs keep logic local]
- Public API rule: [what counts as a public interface and requires extra care]

## Where Tests Live

| Code Area | Test Location | Test Command | Notes |
| --- | --- | --- | --- |
| `[code path]` | `[test path]` | `[command]` | [unit, integration, e2e, fixtures] |
| `[code path]` | `[test path]` | `[command]` | [unit, integration, e2e, fixtures] |

Testing expectations:

- Add or update tests when behavior changes.
- Run the narrowest test command first.
- Run broader validation when touching shared code, public interfaces, or risky areas.

## Common Entry Points

- Local app: `[command or file path]`
- API/server entry: `[command or file path]`
- CLI entry: `[command or file path]`
- Background worker: `[command or file path]`
- Main configuration: `[file path]`
- Environment example: `[file path]`

## Important Data Flows

1. [User/request/event] enters at `[entry point]`.
2. [Main service/module] handles `[responsibility]`.
3. [Storage/external service] is called through `[boundary/module]`.
4. [Response/output/side effect] is produced by `[module]`.

Add only flows that help Codex avoid wrong edits.

## Dangerous Areas

Treat these areas with extra care:

- `[path]` - [why it is risky: data loss, auth, billing, migrations, privacy, performance, etc.]
- `[path]` - [why it is risky]
- `[command]` - [why it is risky]

Rules for risky areas:

- Ask before changing behavior that affects data loss, auth, billing, security, privacy, migrations, or external integrations.
- Prefer adding tests or dry-run validation before changing risky code.
- State assumptions clearly if the ownership boundary is unclear.

## Agent Navigation Rules

- Start with this file, `AGENTS.md`, and the files named in the task.
- Use `rg` or focused file reads before opening large files.
- Do not infer architecture from one file when this map points to a boundary.
- If this map is stale, mention the mismatch and update it as part of the task when useful.

## Last Updated

- Date: [YYYY-MM-DD]
- Updated by: [person or agent]
- Reason: [why this map changed]
