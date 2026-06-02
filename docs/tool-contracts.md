# Tool Contracts

## Tool Adapter Goal

A TraceForge tool is a controlled capability exposed to agents. Tools must be traceable, permission-aware, testable, and provider-independent.

## Planned Tool Adapter Contract

A future implementation should define a tool contract with these fields:

| Field | Purpose |
|---|---|
| id | Stable tool identifier |
| name | Human-readable name |
| description | Agent-facing capability description |
| inputSchema | Runtime-validated input schema |
| permissionPolicy | Required permission level |
| execute | Tool execution function |
| timeoutMs | Maximum duration |
| emits | Expected trace event names |

## MVP Tools

| Tool | Required Scope |
|---|---|
| filesystem.read | Read workspace-scoped files |
| filesystem.write | Write workspace-scoped files after approval |
| git.status | Read Git status |
| git.diff | Read Git diff |
| git.branch | Read current branch |
| shell.exec | Run command after approval and timeout |

## Tool Execution Flow

```text
Agent requests tool
  → Validate input
  → Determine permission level
  → Emit permission.requested
  → User/config decision
  → Emit permission.decided
  → Execute tool if allowed
  → Capture stdout/stderr/result
  → Emit tool.completed or tool.failed
```

## Tool Design Rule

Tools must not call models directly. Tools perform capability work; orchestration decides when to call models.
