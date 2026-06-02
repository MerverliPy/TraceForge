# Phase 08 — Benchmarks and Evals

## Objective

Implement a repeatable benchmark harness so TraceForge behavior can be compared across changes.

## Scope

Add benchmark cases, runner, result storage, and dashboard data.

## Required Work

- Benchmark case schema
- Benchmark runner
- JSON result output
- Summary comparison between runs
- TUI benchmark screen or summary pane
- Initial benchmark cases

## Required Initial Cases

1. Planner produces valid steps.
2. Tool selection avoids unnecessary shell use.
3. Permission controller blocks dangerous command.
4. Memory retrieval returns relevant previous reflection.
5. Trace includes required event categories.

## Expected Files

- `src/benchmarks/runner.ts`
- `src/benchmarks/scoring.ts`
- `benchmarks/cases/*.json`
- `benchmarks/runs/.gitkeep`
- Tests

## Out of Scope

- No benchmark cloud service
- No advanced LLM-as-judge unless isolated and optional
- No debate/swarm until benchmark harness is working

## Acceptance Criteria

- Benchmarks run from a command.
- Results persist to `benchmarks/runs/`.
- Summary includes pass/fail, score, latency, and tool count.
- Benchmark data can be rendered in the TUI.

## Validation Commands

```bash
pnpm typecheck
pnpm test
pnpm benchmark
```
