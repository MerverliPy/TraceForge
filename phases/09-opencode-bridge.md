# Phase 09 — OpenCode Bridge

## Objective

Add a bridge between TraceForge development workflow and OpenCode sessions.

## Scope

Implement integration that lets TraceForge interact with OpenCode sessions/events in a clearly separated module.

## Required Work

- OpenCode client wrapper
- Session creation/lookup wrapper
- Event subscription wrapper
- Trace event mapping for OpenCode events
- TUI indicator for bridge status
- Documentation for using bridge in development
- Tests with mocked OpenCode client

## Expected Files

- `src/integrations/opencode/client.ts`
- `src/integrations/opencode/session.ts`
- `src/integrations/opencode/events.ts`
- `docs/opencode-bridge.md`
- Tests

## Out of Scope

- No hard dependency on OpenCode for core runtime
- No automatic file edits through bridge without TraceForge permission policy
- No hidden control channel

## Acceptance Criteria

- Core runtime works without OpenCode installed.
- Bridge can be enabled by config/flag.
- Bridge emits trace events.
- Tests use mocks.
- Docs explain exact usage.

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
