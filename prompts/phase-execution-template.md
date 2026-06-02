# Phase Execution Prompt Template

Paste this into OpenCode for any phase:

```text
Read AGENTS.md, IMPLEMENTATION_PHASES.md, docs/architecture-blueprint.md, docs/security-model.md, and <PHASE_FILE>.

Implement only <PHASE_NAME>.

Before editing, respond with:
1. phase boundary
2. target files
3. acceptance criteria mapping
4. validation commands

Then execute the implementation.

After editing, run the validation commands and provide the Phase Completion Report from AGENTS.md.
```
