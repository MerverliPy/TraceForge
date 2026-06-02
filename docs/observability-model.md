# Observability Model

## Goal

TraceForge should expose what the agent did, why it did it, and what it cost.

## Internal Observability Primitive

The core primitive is a `TraceEvent` emitted by all major runtime operations.

## Required Event Categories

| Category | Examples |
|---|---|
| Run | run.started, run.completed, run.failed |
| Planner | planner.started, planner.plan.created, planner.replanned |
| Worker | worker.started, worker.completed, worker.failed |
| Model | model.request.started, model.request.completed |
| Tool | tool.started, tool.completed, tool.failed |
| Permission | permission.requested, permission.approved, permission.denied |
| Memory | memory.query.started, memory.result.returned, memory.write.completed |
| Reflection | reflection.started, reflection.completed |
| Benchmark | benchmark.started, benchmark.case.completed, benchmark.completed |

## Event Shape Requirements

Each event should eventually include:

- id
- run id
- parent id
- timestamp
- category
- name
- status
- duration if applicable
- attributes
- redacted payload summary
- error summary if failed

## Trace Store Requirements

The trace store should support:

- Append event
- Query by run
- Query by parent span
- Export run as JSON
- Export run as NDJSON
- Later: export as OpenTelemetry spans

## TUI Rule

The TUI should derive display state from trace events, not from direct runtime internals.
