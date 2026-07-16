# Research Budget Workflow

Purpose: keep current research targeted, fresh, and proportional to the implementation decision it supports.

Use this for tasks involving changing APIs, software behavior, dependencies, policies, standards, prices, schedules, or other facts that may have changed.

## 1. Define The Decision

Write down:

```text
Decision needed:
[what implementation or recommendation must be chosen]

Freshness risk:
[what may have changed and the relevant date, release, or trigger]

Done when:
[the evidence needed to make the decision]
```

Do not research broadly until the decision and stopping condition are clear.

## 2. Spend The Budget In Order

1. Start with the official documentation, changelog, specification, repository source, or primary data.
2. Use no more than three external sources by default.
3. Prefer current, primary, directly relevant sources.
4. Use additional sources only when the decision is high-risk, sources conflict, or the available evidence is insufficient. Record the reason for the exception.

Track each source:

| Source | Date checked | Claim supported | Reliability or caveat |
| --- | --- | --- | --- |
| [URL, file, or command] | [YYYY-MM-DD] | [specific claim] | [caveat] |

For reusable or time-sensitive findings, copy the source record and conclusion into `docs/agent-context/current-research.md`.

## 3. Make The Decision

After each source, ask:

- Does this support, reject, or change the implementation choice?
- Is the remaining uncertainty material to the decision?
- Would another source plausibly change the outcome?

Stop researching when the evidence supports the decision and additional research is unlikely to change it. State unresolved uncertainty instead of researching indefinitely.

## 4. Escalation Rule

Exceed the default source budget only when:

- official and other credible sources conflict;
- the decision affects security, privacy, billing, legal compliance, data loss, or production safety; or
- no source provides enough evidence to choose safely.

When escalating, record the reason, the added sources, and the new stopping condition.

## Done When

- The implementation decision is explicit.
- The strongest relevant source is recorded.
- The default budget was respected or an exception was justified.
- Remaining uncertainty, project impact, and the next recheck trigger are recorded.
