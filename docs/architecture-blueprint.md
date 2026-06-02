# Architecture Blueprint

## Design Principle

TraceForge should be designed trace-first. Runtime components should emit structured events rather than hiding behavior inside opaque calls.

## Top-Level Runtime

```text
TraceForgeApp
  ├─ CLI entry
  ├─ TUI renderer
  ├─ Runtime coordinator
  ├─ Trace event bus
  ├─ Orchestrator
  │   ├─ Planner
  │   ├─ Worker router
  │   ├─ Reducer
  │   └─ Reflection controller
  ├─ Model adapter registry
  ├─ Tool registry
  ├─ Permission controller
  ├─ Memory store
  └─ Benchmark runner
```

## Internal Boundaries

| Boundary | Responsibility |
|---|---|
| Core contracts | Shared types and schemas |
| Event bus | Runtime event publication and subscription |
| Trace store | Append-only run records |
| Orchestration | Planner, workers, reducer, routing |
| Models | Provider-independent model calls |
| Tools | Filesystem, Git, shell, API adapters |
| Memory | Run summaries, reflections, retrieval |
| TUI | Display state derived from trace events |
| Benchmarks | Repeatable eval tasks and score comparison |
| OpenCode bridge | Development/session integration only |

## Required Runtime Invariant

The TUI must not be coupled directly to planner/worker internals. It should render derived state from the trace/event stream.

## Data Flow

```text
User task
  → CLI/TUI input
  → RunContext created
  → Relevant memory loaded
  → Planner emits plan
  → Worker tasks execute
  → Tools/models emit events
  → Reducer creates final answer/artifact
  → Reflection pass runs
  → Memory stores summary
  → Benchmark runner optionally records score
```

## Coordination Choice

The default MVP coordination pattern is planner → worker.

Reason:

- Easier to trace
- Easier to debug in a TUI
- Easier to benchmark
- Lower implementation risk
- Stronger fit for a 2–4 week MVP

Debate and swarm should be separate strategies implemented after the benchmark harness exists.

## Planned Runtime Interfaces

The implementation should introduce contracts before concrete logic:

- `RunContext`
- `TraceEvent`
- `TraceSpan`
- `Planner`
- `Worker`
- `Reducer`
- `ModelAdapter`
- `ToolAdapter`
- `PermissionRequest`
- `MemoryRecord`
- `ReflectionRecord`
- `BenchmarkCase`
- `BenchmarkResult`

## MVP Dependency Rule

Every dependency must map to one of these categories:

- CLI/TUI
- Runtime validation
- Testing
- Model provider
- Local database
- Observability
- Developer tooling

No dependency should be added because it is “nice to have.”
