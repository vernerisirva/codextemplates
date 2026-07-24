# MCP and Tool Audit

Purpose: keep useful external capabilities available without calling tools or loading context that does not help the task.

Run this audit monthly, after installing a plugin or MCP server, or when sessions feel slower or noisier.

## Inventory

```bash
codex mcp list
codex plugin list | rg "installed, enabled|installed, disabled"
```

For each item, ask:

- Was it useful in a real task during the last 30 days?
- Does it provide data or actions that local files and shell commands cannot?
- Is its trigger narrow and obvious?
- Does its value justify added context, latency, approvals, and maintenance?
- Is another enabled tool already covering the same job?

## Decision Rules

- **Keep enabled:** frequently useful infrastructure with a clear, unique purpose.
- **Use on demand:** specialized capability that is valuable only for matching tasks.
- **Disable or uninstall:** unused, redundant, unreliable, or costly capability with no expected near-term task.
- Do not remove a tool merely because it is infrequent. Prefer a clear on-demand trigger when the capability is unique.

## Default Usage Policy

- Start with local files and shell tools for local repository questions.
- Use one external tool when it provides required current, private, or service-specific information.
- Do not call multiple tools for the same fact unless validation or conflicting evidence requires it.
- Do not browse, search connectors, or discover tools speculatively.
- Stop tool research when the implementation decision or answer is supported.

## Audit Record

Audit date: [YYYY-MM-DD]

| Capability | Decision | Use when | Evidence or reason |
| --- | --- | --- | --- |
| [MCP server, plugin, connector, or built-in tool] | [Keep enabled / Use on demand / Disable or uninstall] | [Clear trigger] | [Recent use, unique value, redundancy, or cost] |

Conclusion: [Keep the current setup or name the exact configuration changes justified by the audit.]

Official guidance reviewed: 2026-07-24. [Codex MCP documentation](https://learn.chatgpt.com/docs/extend/mcp) describes MCP as access to external tools and context, with configuration shared across local Codex clients.
