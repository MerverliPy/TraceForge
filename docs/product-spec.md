# Product Specification

## Name

TraceForge

## One-Line Description

TraceForge is a trace-native, TUI-first AI agent framework for building, inspecting, benchmarking, and improving agent workflows from the terminal.

## Primary User

A developer who wants to build agent systems with strong introspection, visible execution traces, local memory, safe tool use, and benchmark-driven iteration.

## Positioning

TraceForge should not compete as a generic “agent framework.” Its wedge is:

> Every run is a trace. Every trace is visible. Every improvement is benchmarked.

## Core Differentiators

1. TUI-first runtime visibility
2. Planner → worker orchestration as the default coordination model
3. Trace event bus as the internal contract
4. Reflection and tool-selection improvement loops
5. Local-first memory using inspectable storage
6. Safe filesystem, Git, and shell tools
7. Benchmarks before advanced multi-agent modes
8. OpenCode-friendly implementation workflow

## MVP Definition

The MVP is complete when a user can:

1. Start TraceForge from the terminal.
2. Submit a task through the CLI/TUI.
3. See a live run tree in the TUI.
4. See trace events as planner, worker, model, and tool actions occur.
5. Use at least one model provider adapter.
6. Execute filesystem, Git, and shell tools behind permission checks.
7. Store and retrieve run summaries from local memory.
8. Run a benchmark suite and see benchmark summaries.
9. Run a reflection pass after a task.
10. Use OpenCode bridge integration as a development workflow.

## Non-Goals for MVP

- No hosted SaaS
- No browser UI
- No distributed worker cluster
- No plugin marketplace
- No dense-vector database requirement
- No autonomous unsupervised code mutation
- No default network-enabled shell sandbox
- No debate/swarm as default execution mode

## Planned Modes

| Mode | MVP Status | Purpose |
|---|---|---|
| Hierarchical planner → worker | Required | Default reliable orchestration model |
| Debate | Later | Compare proposals and critiques against benchmark outcomes |
| Swarm | Later | Parallel specialist execution when task decomposition is mature |

## Success Metrics

| Metric | Target for MVP |
|---|---|
| Startup friction | Clone → first run in under 5 commands after implementation |
| Trace visibility | Every model/tool/planner step emits a structured event |
| Safety | Shell and write actions require permission gates |
| Benchmarkability | At least 5 benchmark tasks can run repeatedly |
| Contributor clarity | New contributor can pick up a labeled issue without architecture reverse-engineering |
