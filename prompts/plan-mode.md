# Plan Mode Prompt

Use this after entering Plan Mode for a task that meets `profiles/plan-mode-trigger-rules.md`.

```text
Plan only. Do not edit files, run mutating commands, install dependencies, commit, push, or begin implementation. Read-only inspection is allowed.

Goal:
[one concrete outcome]

Known context:
[issue, symptoms, files, architecture, or prior decisions]

Constraints:
[scope limits, compatibility, safety, deadlines, or conventions]

Done when:
[observable completion criteria]

Research/tool budget:
[optional limit for browsing, file reads, or experiments]

Planning instructions:
1. Read the applicable AGENTS.md and validation guidance first.
2. Identify the smallest file set needed to understand and implement the task.
3. Inspect only that file set. Expand it only when a specific unanswered question requires another file.
4. Ask focused questions only when the answer could materially change the plan.
5. Do not make changes while planning.

Return:

1. Understanding
   - Restate the goal, constraints, and done-when criteria.
   - Name assumptions that materially affect the plan.

2. Smallest file set
   - List each file or directory to inspect or change.
   - Give one sentence explaining why each is needed.

3. Implementation path
   - Provide ordered, concrete steps.
   - Name the affected files and intended behavior for each step.
   - Keep optional improvements separate from required work.

4. Risks and open questions
   - Identify regression, security, data, compatibility, performance, or scope risks that actually apply.
   - State the smallest mitigation for each risk.

5. Validation
   - Give exact commands or manual checks in narrow-to-broad order.
   - Explain what each check proves.

6. Approval gate
   - End with: "Plan ready. Waiting for approval before editing or implementation."

Stop after presenting the plan. Do not execute any step until I explicitly approve implementation.
```

Official guidance reviewed: 2026-07-23. Codex Plan Mode is intended to gather context, ask clarifying questions, and build a plan before implementation.
