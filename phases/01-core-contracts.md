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

## Test Expansion Checklist

### Schema validation tests
- [ ] `runId` / `spanId` primitive: must reject empty strings, must accept valid ULID/UUID formats
- [ ] `RunStatus`: must accept only defined status values, must reject unknown strings
- [ ] `TraceEventCategory`: must accept only defined categories
- [ ] `ModelRequest` / `ModelResponse`: must validate required fields (model, messages), reject missing provider
- [ ] `ToolRequest` / `ToolResult`: must validate tool id, input schema, reject missing permission policy
- [ ] `PlannerPlan` / `PlanStep`: must validate ordered step array, reject circular dependencies
- [ ] `WorkerTask` / `WorkerResult`: must validate task id and status transitions
- [ ] `PermissionRequest` / `PermissionDecision`: must validate level enum (allow/ask/deny)
- [ ] `MemoryRecord`: must validate content, timestamp, and run reference
- [ ] `BenchmarkCase` / `BenchmarkResult`: must validate expected output shape and score fields

### Config validation tests
- [ ] Config schema rejects unknown top-level keys
- [ ] Config schema validates model adapter config shape
- [ ] Config schema validates tool policy entries (level, allowlist, denylist)
- [ ] Config schema rejects empty config files
- [ ] Config schema validates timeout and truncation values are positive

### Contract boundary tests
- [ ] No provider-specific types (OpenAI, Anthropic, Ollama) leak into core contract modules
- [ ] All contracts export Zod schemas with `.parse()` and `.safeParse()` available
- [ ] All contracts are tree-shakeable (type-only imports work)

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
