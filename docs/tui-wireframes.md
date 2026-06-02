# TUI Wireframes

## Primary Dashboard

```text
┌ TraceForge ─ run: active ─ mode: hierarchical ─ provider: selected ─────────────┐
│ Run Tree                    │ Trace Timeline                 │ Metrics          │
│ ├─ planner                  │ 00:00 run.started              │ tokens           │
│ ├─ worker.filesystem        │ 00:01 planner.plan.created     │ latency          │
│ ├─ worker.git               │ 00:03 tool.git.diff.started    │ tool success     │
│ ├─ worker.shell             │ 00:07 worker.completed         │ cost             │
│ └─ reflector                │ 00:09 reflection.created       │ benchmark score  │
├─────────────────────────────┼────────────────────────────────┼──────────────────┤
│ Prompt / Plan               │ Tool Input / Output            │ Permissions      │
│ <selected node details>     │ <selected event payload>       │ <pending gates>  │
└─────────────────────────────┴────────────────────────────────┴──────────────────┘
```

## Required Panes

| Pane | Purpose |
|---|---|
| Run Tree | Hierarchical view of planner, workers, tools, reflection |
| Trace Timeline | Ordered event stream |
| Metrics | Tokens, latency, cost, tool success, benchmark status |
| Details | Selected node/event details |
| Permissions | Pending filesystem, Git, and shell approvals |
| Benchmarks | Current and previous benchmark summaries |

## Interaction Model

| Key | Action |
|---|---|
| Arrow keys | Move selection |
| Tab | Switch pane |
| Enter | Expand/collapse node or inspect event |
| a | Approve pending permission |
| d | Deny pending permission |
| r | Replay selected trace later |
| b | Open benchmark summary |
| q | Quit |

## MVP TUI Rule

The first implementation does not need visual polish. It must prove that trace events can drive live UI state.
