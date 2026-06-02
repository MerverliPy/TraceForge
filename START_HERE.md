# Start Here

This repository is a **no-code startup scaffold** for TraceForge.

Use this sequence:

1. Open the repository in a terminal.
2. Start OpenCode with `opencode`.
3. Ask OpenCode to read `AGENTS.md`.
4. Execute one phase at a time from `phases/`.
5. After each phase, run the review command from `.opencode/commands/phase-review.md`.
6. Commit after every completed phase.

## First OpenCode Prompt

```text
Read AGENTS.md, README.md, docs/product-spec.md, docs/architecture-blueprint.md, docs/security-model.md, and phases/00-repository-foundation.md.

You are implementing TraceForge from a phase scaffold.
Do not implement future phases.
Do not create undocumented architecture.
First, produce a concise Phase 00 execution plan.
Then execute Phase 00 only.
After changes, provide:
- summary
- files changed
- validation commands
- risks
- next phase readiness
```

## Strict Boundary

This scaffold intentionally does not contain runtime implementation code. Do not treat this repository as already implemented.
