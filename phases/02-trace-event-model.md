# Phase 02 — Trace Event Model

## Objective

Implement the trace event bus and in-memory trace store that all future runtime behavior will use.

## Scope

Build the internal observability foundation before building orchestration.

## Required Work

- Event bus interface
- Event subscription mechanism
- Append-only in-memory trace store
- Run lifecycle helpers
- Parent/child event relationships
- JSON export for one run
- Tests for event order and parent relationships

## Expected Files

- `src/core/events.ts` update if needed
- `src/observability/event-bus.ts`
- `src/observability/trace-store.ts`
- `src/observability/exporters.ts`
- Unit tests

## Out of Scope

- No OpenTelemetry export yet
- No TUI
- No runtime orchestration
- No persistent storage

## Acceptance Criteria

- Can start a run, append child events, complete run.
- Can subscribe to events.
- Can export run events as JSON.
- Tests prove order and relationships.

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
