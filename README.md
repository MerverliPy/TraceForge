# TraceForge

TraceForge is a planned **TUI-first AI agent framework** where every agent run is designed around traces, inspection, reflection, benchmarks, and safe tool execution.

This repository intentionally contains **no TraceForge runtime implementation code** yet. It is a startup repository designed to be opened in an OpenCode terminal session and executed phase-by-phase by coding agents.

## Repository Status

Current state: **Implementation-planning scaffold only**

Included:

- Product definition
- Architecture blueprint
- TUI wireframes
- Security model
- Tool contract specifications
- Model adapter specifications
- Memory and reflection design
- Observability design
- OpenCode agent instructions
- OpenCode implementation commands
- GitHub issue templates
- Ordered implementation phases

Not included:

- No `src/` implementation
- No runtime classes
- No package implementation
- No model adapter implementation
- No tool adapter implementation
- No TraceForge CLI implementation

## Intended Tech Stack

The implementation phases currently assume this stack:

| Layer | Planned Choice |
|---|---|
| Language | TypeScript |
| Runtime | Node.js 22+ |
| Package manager | pnpm |
| TUI | Ink |
| Config validation | Zod |
| Testing | Vitest |
| Local memory | SQLite + FTS5 |
| Observability | Trace event schema + OpenTelemetry export later |
| API models | OpenAI + Anthropic |
| Local models | Ollama |
| Coding-agent workflow | OpenCode |

The stack is documented as a plan. The coding agent should create the actual implementation during the phases.

## Start in OpenCode

From the repository root:

```bash
opencode
```

Then run the first phase using the local command prompt:

```text
/phase-start phases/00-repository-foundation.md
```

Recommended first prompt inside OpenCode:

```text
Read AGENTS.md, docs/product-spec.md, docs/architecture-blueprint.md, and phases/00-repository-foundation.md. Do not implement later phases. Produce a phase plan, then execute only Phase 00.
```

## Phase Execution Rule

Each phase must end with:

1. A short implementation summary
2. Files created or changed
3. Tests or validations added
4. Open questions
5. Next phase readiness checklist

Do not skip ahead. Do not implement features from later phases unless the current phase explicitly requires a placeholder contract.

## Implementation Phases

| Phase | File | Goal |
|---|---|---|
| 00 | `phases/00-repository-foundation.md` | Initialize actual TypeScript project foundation |
| 01 | `phases/01-core-contracts.md` | Define core runtime contracts and schemas |
| 02 | `phases/02-trace-event-model.md` | Build trace/event model and run lifecycle contracts |
| 03 | `phases/03-cli-and-tui-shell.md` | Implement CLI entry and TUI layout shell |
| 04 | `phases/04-model-adapter-layer.md` | Implement model adapter interface and providers |
| 05 | `phases/05-tool-system-and-permissions.md` | Implement tools, permissions, and sandbox policy |
| 06 | `phases/06-planner-worker-runtime.md` | Implement planner → worker orchestration |
| 07 | `phases/07-memory-and-reflection.md` | Implement memory, compression, retrieval, reflection |
| 08 | `phases/08-benchmarks-and-evals.md` | Implement benchmark runner and eval dashboard data |
| 09 | `phases/09-opencode-bridge.md` | Implement OpenCode bridge and session integration |
| 10 | `phases/10-release-hardening.md` | Harden, document, test, and prepare public release |

## Target Repository Shape After Implementation

See `docs/target-tree.md` for the desired implementation tree. The actual files should be created by OpenCode agents during the phase sequence.

## Contributing

TraceForge is planned as a contributor-first open-source project. See `CONTRIBUTING.md` and `tasks/initial-issues.md`.

## License

Apache-2.0. See `LICENSE`.
