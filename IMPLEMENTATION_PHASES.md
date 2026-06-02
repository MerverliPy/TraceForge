# TraceForge Implementation Phases

This file is the master execution map. Each phase has a dedicated file in `phases/`.

## Execution Contract

- Execute phases in order.
- Commit after each phase.
- Use tests as phase gates.
- Keep the architecture trace-first.
- Do not implement future-phase behavior early.

## Phase Overview

| Phase | Name | Primary Output |
|---|---|---|
| 00 | Repository Foundation | TypeScript project setup |
| 01 | Core Contracts | Shared types and schemas |
| 02 | Trace Event Model | Event bus and trace store |
| 03 | CLI and TUI Shell | Terminal dashboard rendering synthetic events |
| 04 | Model Adapter Layer | OpenAI, Anthropic, Ollama behind common interface |
| 05 | Tool System and Permissions | Filesystem, Git, shell with safety gates |
| 06 | Planner → Worker Runtime | First real orchestration loop |
| 07 | Memory and Reflection | SQLite memory and self-critique loop |
| 08 | Benchmarks and Evals | Repeatable benchmark harness |
| 09 | OpenCode Bridge | Session/event integration |
| 10 | Release Hardening | Alpha release readiness |

## Recommended Commit Pattern

```text
phase-00: initialize repository foundation
phase-01: add core runtime contracts
phase-02: add trace event bus and trace store
phase-03: add CLI and TUI shell
phase-04: add model adapter layer
phase-05: add tool system and permissions
phase-06: add planner worker runtime
phase-07: add memory and reflection
phase-08: add benchmarks and evals
phase-09: add opencode bridge
phase-10: harden alpha release
```

## Stop Conditions

Stop and report before continuing if:

- A phase requires a dependency not listed in the design docs.
- A security boundary becomes unclear.
- A test requires real API credentials.
- A design conflict appears between phase docs and architecture docs.
- A later phase seems necessary to complete current acceptance criteria.
