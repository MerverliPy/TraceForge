# Phase 01 — Core Contracts

## Objective

Define the core TypeScript contracts and validation schemas that future runtime components will use.

## Scope

Create contract-only modules. Keep concrete behavior minimal.

## Required Contracts

- Run id / span id primitives
- Run status
- Trace event category and status
- Model request/response shape
- Tool request/result shape
- Planner plan and plan step shape
- Worker task/result shape
- Permission request/decision shape
- Memory record shape
- Benchmark case/result shape

## Expected Files

- `src/core/types.ts`
- `src/core/events.ts`
- `src/core/run-context.ts`
- `src/core/errors.ts`
- `src/config/schema.ts`
- Tests for schema validation

## Out of Scope

- No real model calls
- No real tool calls
- No orchestration loop
- No TUI rendering

## Acceptance Criteria

- Contracts are documented.
- Runtime schemas validate external/config-facing inputs.
- Unit tests cover valid and invalid examples.
- No provider-specific types leak into core contracts.

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
