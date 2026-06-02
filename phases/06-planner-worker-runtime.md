# Phase 06 — Planner → Worker Runtime

## Objective

Implement the first real agent orchestration loop using planner → worker hierarchy.

## Scope

Build one default planner, worker router, worker execution loop, and reducer.

## Required Work

- Planner interface
- Default planner implementation
- Worker interface
- Worker router
- Reducer
- Run loop
- Trace events for each stage
- Basic task execution with model adapter and tools
- Tests using fake model and fake tools

## Expected Files

- `src/orchestration/planner.ts`
- `src/orchestration/worker.ts`
- `src/orchestration/router.ts`
- `src/orchestration/reducer.ts`
- `src/orchestration/strategies/hierarchical.ts`
- Integration tests

## Out of Scope

- No debate mode
- No swarm mode
- No advanced planning/search
- No autonomous code mutation

## Acceptance Criteria

- A task can produce a plan.
- Plan steps can be routed to workers.
- Workers can use allowed tools and model calls.
- Reducer creates a final run result.
- Full run emits trace events visible in the TUI.
- Tests prove happy path and one failure path.

## Validation Commands

```bash
pnpm typecheck
pnpm test
pnpm dev
```
