# Validation

Purpose: tell Codex the narrowest command that proves a change is complete.

Replace bracketed values with commands that work in this repository. Remove rows that do not apply rather than preserving stale placeholders.

## Command Map

| Check | Command | Run when |
| --- | --- | --- |
| Install | `[install command]` | Dependencies, manifests, or lockfiles change; or a fresh checkout needs setup. |
| Typecheck | `[typecheck command]` | Typed code, public interfaces, generated types, or build contracts change. |
| Lint | `[lint command]` | Source, configuration, documentation, or formatting-sensitive files change. |
| Unit tests | `[unit test command]` | Focused behavior changes or a regression test can prove the fix. |
| Integration tests | `[integration test command]` | The change crosses modules, services, storage, queues, routes, or external boundaries. |
| Build/package | `[build command]` | Bundling, packaging, generated assets, framework configuration, or public exports change. |

## Package-Specific Commands

| Area | Working directory | Command | Run when |
| --- | --- | --- | --- |
| `[app/package]` | `[path]` | `[command]` | [trigger] |

Add rows only for commands that must run from a specific app, package, or service directory.

## Checks By Change Type

| Change | Minimum validation |
| --- | --- |
| Documentation only | `git diff --check`, configured docs lint, and readback of changed files. |
| Small code change | Narrow unit test plus lint. |
| Shared or cross-module behavior | Relevant package tests, integration tests, and typecheck. |
| UI or visual behavior | Component test plus browser, end-to-end, or exact manual visual check. |
| Data or migration | Migration validation, dry run when available, and relevant integration tests. |
| Configuration or dependency | Install, typecheck, tests, and build as affected. |

## Escalation Rule

Start with the narrowest command that covers the changed behavior. Escalate when:

- The narrow check fails or does not cover the behavior.
- Shared code, public interfaces, or ownership boundaries are affected.
- The change affects auth, billing, privacy, security, data formats, or migrations.
- The task crosses packages, services, storage, or external integrations.

Do not run destructive commands without explicit approval. Prefer dry runs, backups, fixtures, or local test data.

## Completion Gate

A task is complete when:

- The requested behavior or artifact exists.
- Relevant validation has passed.
- Changed files have been inspected.
- `git diff --check` passes for text changes.
- Tests cover changed behavior when applicable.
- Skipped validation and its reason are reported.

## Last Updated

- Date: [YYYY-MM-DD]
- Updated by: [person or agent]
- Reason: [why validation guidance changed]
