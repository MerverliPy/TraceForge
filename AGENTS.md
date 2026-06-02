# TraceForge Agent Instructions

You are working inside the TraceForge repository.

TraceForge is a planned TUI-first AI agent framework. This repository begins as a planning scaffold and must be implemented in ordered phases.

## Non-Negotiable Rules

1. Do not implement multiple phases at once.
2. Do not introduce runtime implementation before Phase 00 requests it.
3. Do not create hidden architecture not documented in `docs/` or the current phase file.
4. Do not add dependencies without explaining why they are required for the current phase.
5. Do not execute shell commands that mutate files outside the repository root.
6. Do not add networked services unless the current phase explicitly permits it.
7. Do not hardcode API keys, tokens, provider credentials, or local paths.
8. Do not remove safety or permission checks to make tests pass.
9. Do not skip tests when a phase requests validation.
10. Do not mark a phase complete unless its acceptance criteria are satisfied.

## Implementation Style

Prefer:

- Small, reviewable changes
- Explicit interfaces before concrete implementations
- Testable units
- Trace-first data flow
- Plain, documented contracts
- Local-first operation
- Safe defaults

Avoid:

- Large abstractions without usage
- Multi-agent complexity before benchmarks exist
- Long-lived global state
- Provider-specific leakage into core runtime
- Shell execution without approval boundaries
- Memory systems that cannot be inspected locally

## Planned Architecture

The planned runtime shape is:

```text
CLI / TUI
  → Core runtime
    → Event bus / trace store
    → Planner
      → Workers
        → Tools
        → Model adapters
    → Memory
    → Reflection
    → Benchmarks
```

## OpenCode Working Mode

When asked to implement a phase:

1. Read the phase file completely.
2. Read any referenced docs.
3. Restate the phase boundary.
4. Identify files that will be created or modified.
5. Implement only that phase.
6. Run validation.
7. Report results.

## Completion Report Format

At the end of each implementation phase, respond with:

```md
## Phase Completion Report

### Phase
<phase id and name>

### Summary
<what changed>

### Files Changed
<list>

### Validation
<commands run and results>

### Acceptance Criteria
- [x] criterion 1
- [x] criterion 2

### Risks / Follow-ups
<items>

### Ready for Next Phase
Yes/No, with reason
```
