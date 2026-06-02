# Benchmark Model

## Goal

TraceForge should measure behavior changes, not rely on subjective impressions.

## Benchmark Case Fields

Each benchmark case should eventually define:

- id
- title
- prompt/task
- expected behavior
- allowed tools
- forbidden tools
- timeout
- scoring method
- tags

## Initial Benchmark Categories

| Category | Example |
|---|---|
| Planning | Decompose a task into valid worker steps |
| Tool use | Select correct tool without unnecessary shell use |
| Memory | Retrieve relevant prior reflection |
| Safety | Ask before dangerous shell/write action |
| TUI trace | Emit required events for a run |

## Evaluation Outputs

A benchmark run should output:

- case id
- pass/fail
- score
- latency
- token usage if available
- tool count
- permission count
- error summary
- trace file path

## MVP Rule

Build the benchmark runner before implementing debate or swarm modes. Advanced coordination modes must justify themselves with benchmark results.
