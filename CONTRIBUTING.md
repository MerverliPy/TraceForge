# Contributing to TraceForge

TraceForge starts as a phase-driven implementation project.

## Contribution Rules

- Pick one issue or one phase task.
- Do not combine unrelated phases.
- Include tests for implementation changes.
- Include trace examples for behavior changes when practical.
- Keep safety defaults intact.

## Local Workflow

After Phase 00 is implemented, the expected workflow will be:

```bash
pnpm install
pnpm typecheck
pnpm test
```

Before Phase 00, this repository is documentation-only.

## Pull Request Expectations

A PR should include:

- Clear description
- Linked issue/phase
- Acceptance criteria checklist
- Validation commands run
- Screenshots or trace examples for TUI changes
- Security notes for tool/shell changes

## Architecture Review

Changes touching orchestration, tools, memory, or observability should be reviewed against `docs/architecture-blueprint.md` and `docs/security-model.md`.
