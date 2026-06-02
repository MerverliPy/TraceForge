# Security Policy

TraceForge will eventually execute model-selected tools, including filesystem, Git, and shell commands. Security-sensitive changes must be reviewed carefully.

## Report a Vulnerability

Open a private security advisory in GitHub if available, or contact the maintainer listed in the repository profile.

## High-Risk Areas

- Shell command execution
- Filesystem writes/deletes
- Git write operations
- Environment variable access
- Secret logging
- Trace payload storage
- Memory persistence
- External API integrations

## Required Security Defaults

- Shell execution is approval-gated.
- File writes are approval-gated.
- Workspace path boundaries are enforced.
- Secrets are redacted from logs/traces/memory.
- Tool execution emits audit trace events.
- Network access is not assumed safe.
