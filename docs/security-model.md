# Security Model

## Security Objective

TraceForge should make powerful tool execution possible without normalizing unsafe defaults.

## Permission Levels

| Level | Meaning |
|---|---|
| allow | Action can run without interactive approval |
| ask | Action requires explicit approval |
| deny | Action is blocked |

## Default Tool Policy

| Tool Area | Default |
|---|---|
| Read files | ask initially, allow after scoped config |
| Write files | ask |
| Delete files | deny until explicit support |
| Git read commands | allow for safe read-only commands |
| Git write commands | ask |
| Shell commands | ask |
| Network access | deny unless phase/config enables it |
| Secrets access | deny |

## Shell Sandbox Requirements

Shell execution must eventually support:

- Working-directory restriction
- Command allowlist/denylist
- Timeout
- Output truncation
- Environment variable filtering
- Optional container backend
- No implicit network access
- Audit event emission before and after execution

## Required Trace Events

Every permission-relevant tool action must emit:

1. Permission requested
2. Permission decision
3. Tool execution started
4. Tool execution completed or failed

## Secret Handling

Never log raw secrets. The implementation should redact values matching configured secret names or common token patterns.

## MVP Safety Boundary

For the first working MVP, shell execution may be primitive, but it must never bypass the permission controller.
