# Validation

Purpose: tell Codex what to run before claiming changes are done in this repository.

Keep this file exact. Replace bracketed commands with commands that actually work in the repo. Remove sections that do not apply.

## Current Commands

### Install

```bash
[install command]
```

Use when:

- Dependencies are missing.
- Lockfiles or dependency manifests change.
- A fresh checkout needs setup.

### Typecheck

```bash
[typecheck command]
```

Use when:

- Typed source files change.
- Public interfaces change.
- Build or generated types may be affected.

### Lint

```bash
[lint command]
```

Use when:

- Source files, config files, docs, or formatting-sensitive files change.
- The task asks for cleanup, style, or consistency.

### Unit Tests

```bash
[unit test command]
```

Use when:

- A small function, component, module, or package behavior changes.
- A regression test can prove the fix.

### Integration Tests

```bash
[integration test command]
```

Use when:

- Multiple modules, services, routes, database layers, queues, or external boundaries are involved.
- The change affects end-to-end behavior.

### Build Or Package

```bash
[build command]
```

Use when:

- Build output, bundling, packaging, generated assets, or deployment behavior may change.
- The task touches framework config, dependency config, or public exports.

## Package-Specific Commands

Record commands that must run from a specific workspace, package, app, or service directory.

| Area | Working Directory | Command | When To Run |
| --- | --- | --- | --- |
| `[app/package name]` | `[path]` | `[command]` | [when this command is required] |
| `[app/package name]` | `[path]` | `[command]` | [when this command is required] |

Example:

```bash
cd apps/web
[package-specific command]
```

## What To Run By Task Type

### Documentation-Only Change

```bash
git diff --check
[docs lint command if configured]
```

Also read back the changed files.

### Small Code Change

```bash
[narrow unit test command]
[lint command]
```

Run the smallest test that proves the behavior first. Escalate only if shared behavior or public interfaces changed.

### Cross-Module Or Shared Behavior Change

```bash
[relevant package/unit tests]
[integration test command]
[typecheck command]
```

Use when the change crosses ownership boundaries or affects shared code.

### UI Or Visual Change

```bash
[component/unit test command]
[browser/e2e/manual visual validation command]
```

Also capture a screenshot or describe the manual visual check when automated visual tests do not exist.

### Data, Migration, Or Destructive Change

```bash
[migration check command]
[dry-run command if available]
[integration test command]
```

Do not run destructive commands unless the user explicitly approves them. Prefer dry runs, backups, fixtures, or local test data.

### Configuration Or Dependency Change

```bash
[install command]
[typecheck command]
[test command]
[build command]
```

Use when manifests, lockfiles, runtime config, CI config, or environment config changes.

## Validation Escalation Rule

Start with the narrowest command that can prove the task. Escalate when:

- The narrow command fails.
- The change affects shared code.
- The change affects public APIs, data formats, auth, billing, privacy, or migrations.
- The task crosses package or service boundaries.
- The first validation command does not actually cover the changed behavior.

## Done-When Criteria

A task is done when:

- The requested behavior or artifact exists.
- The relevant validation command has run and passed.
- Changed files have been read back or inspected.
- `git diff --check` passes when text files changed.
- Tests were added or updated when behavior changed.
- Any skipped validation is named with the reason.
- The final response says what changed and how it was validated.

## Last Updated

- Date: [YYYY-MM-DD]
- Updated by: [person or agent]
- Reason: [why validation guidance changed]
