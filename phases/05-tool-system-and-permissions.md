# Phase 05 — Tool System and Permissions

## Objective

Implement safe, traceable tool execution for filesystem, Git, and shell operations.

## Scope

Build tool registry, permission controller, and MVP tool adapters.

## Required Tools

- `filesystem.read`
- `filesystem.write`
- `git.status`
- `git.diff`
- `git.branch`
- `shell.exec`

## Required Work

- Tool adapter contract
- Tool registry
- Permission request/decision flow
- Workspace path restriction
- Shell timeout
- Shell output truncation
- Trace events around permission and execution
- Tests for denied, approved, failed, and successful tool calls

## Expected Files

- `src/tools/base.ts`
- `src/tools/registry.ts`
- `src/tools/permissions.ts`
- `src/tools/filesystem.ts`
- `src/tools/git.ts`
- `src/tools/shell.ts`
- Unit/integration tests

## Out of Scope

- No Docker sandbox yet unless trivial
- No browser automation
- No external API tools
- No automatic dangerous command approval

## Acceptance Criteria

- Shell commands require approval by default.
- Writes require approval by default.
- Read-only Git commands can be configured as allowed.
- Every tool call emits trace events.
- Tests prove path restriction and permission enforcement.

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
