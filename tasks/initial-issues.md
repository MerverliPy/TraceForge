# Initial GitHub Issues

Use these as the first GitHub issues after creating the repository.

## 1. Phase 00: Initialize TypeScript project foundation

Labels: `phase:00`, `foundation`, `good first issue`

Create package metadata, TypeScript config, test tooling, `.env.example`, and CI foundation. Do not implement runtime behavior.

Acceptance criteria:

- `pnpm install` works
- `pnpm typecheck` works
- `pnpm test` works
- no TraceForge runtime code exists yet

---

## 2. Phase 01: Define core runtime contracts

Labels: `phase:01`, `core`, `contracts`

Define shared contracts for runs, events, models, tools, planner steps, permissions, memory, and benchmarks.

Acceptance criteria:

- contracts are provider-independent
- schemas validate external inputs
- tests cover valid and invalid examples

---

## 3. Phase 02: Implement trace event bus and trace store

Labels: `phase:02`, `observability`, `trace`

Implement append-only event stream and in-memory trace store.

Acceptance criteria:

- can start/complete a run
- can append parent/child events
- can subscribe to events
- can export a run as JSON

---

## 4. Phase 03: Build CLI and TUI shell

Labels: `phase:03`, `tui`, `cli`

Create the first terminal dashboard using synthetic trace events.

Acceptance criteria:

- CLI launches TUI
- dashboard has run tree, trace timeline, metrics, details, permission panes
- UI state is derived from trace events

---

## 5. Phase 04: Add model adapter layer

Labels: `phase:04`, `models`, `providers`

Add provider-independent model adapter contract and adapters for OpenAI, Anthropic, and Ollama.

Acceptance criteria:

- adapters are behind registry
- tests use mocks/fakes
- no test requires real API keys
- model calls emit trace events

---

## 6. Phase 05: Add tool registry and permission controller

Labels: `phase:05`, `tools`, `security`

Implement filesystem, Git, and shell tools behind a permission controller.

Acceptance criteria:

- write and shell actions require approval by default
- workspace path restriction is enforced
- tool actions emit trace events
- tests cover denied and approved flows

---

## 7. Phase 06: Implement planner → worker orchestration

Labels: `phase:06`, `orchestration`, `agent-runtime`

Implement the first real agent execution loop.

Acceptance criteria:

- task produces a plan
- workers execute plan steps
- reducer returns final output
- full run appears in TUI trace

---

## 8. Phase 07: Add memory and reflection

Labels: `phase:07`, `memory`, `self-improvement`

Implement local memory, retrieval, compression, and post-run reflection.

Acceptance criteria:

- run summaries are stored
- reflections are stored
- relevant memory is retrieved before planning
- sensitive data redaction is tested

---

## 9. Phase 08: Add benchmark runner

Labels: `phase:08`, `benchmarks`, `evals`

Implement repeatable benchmark cases and result summaries.

Acceptance criteria:

- benchmark command runs initial cases
- results persist locally
- benchmark summary includes score, latency, tool count
- benchmark data can be shown in TUI

---

## 10. Phase 09: Add OpenCode bridge

Labels: `phase:09`, `opencode`, `integration`

Implement optional OpenCode session/event bridge.

Acceptance criteria:

- core runtime works without OpenCode
- bridge can be enabled separately
- OpenCode events can map into TraceForge trace events
- tests use mocked client

---

## 11. Phase 10: Prepare alpha release

Labels: `phase:10`, `release`, `docs`

Harden docs, tests, CI, security docs, and benchmark baseline.

Acceptance criteria:

- README quickstart is accurate
- security model matches implementation
- CI passes
- benchmark baseline exists
- release checklist is complete
