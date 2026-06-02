# Phase 03 — CLI and TUI Shell

## Objective

Implement the first visible terminal surface without implementing full agent behavior.

## Scope

Create a CLI entry and TUI layout that can render synthetic trace events from the event bus.

## Required Work

- CLI entry command
- TUI app shell
- Run tree pane
- Trace timeline pane
- Metrics pane
- Details pane
- Permission pane placeholder
- Synthetic demo event stream for UI validation

## Expected Files

- `src/cli.tsx`
- `src/tui/app.tsx`
- `src/tui/state/trace-state.ts`
- `src/tui/screens/dashboard.tsx`
- `src/tui/widgets/run-tree.tsx`
- `src/tui/widgets/trace-timeline.tsx`
- `src/tui/widgets/metrics-panel.tsx`
- `src/tui/widgets/permission-prompt.tsx`
- Tests where practical

## Out of Scope

- No model calls
- No real agent orchestration
- No real tool execution

## Acceptance Criteria

- User can run the CLI.
- TUI renders dashboard panes.
- TUI updates from trace events.
- Synthetic run shows planner/worker/tool/reflection sample nodes.
- TUI state is derived from trace events, not hardcoded internal state.

## Validation Commands

```bash
pnpm typecheck
pnpm test
pnpm dev
```
