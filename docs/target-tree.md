# Target Repository Tree After Implementation

This file defines the intended future implementation tree. The startup scaffold does not include these files yet.

```text
traceforge/
  src/
    cli.tsx
    app.tsx
    config/
      env.ts
      schema.ts
    core/
      types.ts
      events.ts
      run-context.ts
      errors.ts
    orchestration/
      planner.ts
      worker.ts
      reducer.ts
      router.ts
      strategies/
        hierarchical.ts
        debate.ts
        swarm.ts
    models/
      base.ts
      openai.ts
      anthropic.ts
      ollama.ts
      registry.ts
    tools/
      base.ts
      filesystem.ts
      git.ts
      shell.ts
      permissions.ts
      registry.ts
    memory/
      sqlite.ts
      retrieval.ts
      compression.ts
      reflections.ts
    improvement/
      self-critique.ts
      tool-ranker.ts
      tuner.ts
    observability/
      trace-store.ts
      otel.ts
      exporters.ts
    benchmarks/
      runner.ts
      scoring.ts
      cases.ts
    integrations/
      opencode/
        client.ts
        session.ts
        events.ts
    tui/
      app.tsx
      state/
        trace-state.ts
      screens/
        dashboard.tsx
        run-detail.tsx
        benchmarks.tsx
      widgets/
        run-tree.tsx
        trace-timeline.tsx
        metrics-panel.tsx
        permission-prompt.tsx
  tests/
    unit/
    integration/
    smoke/
  benchmarks/
    cases/
    runs/
```

## Rule for Coding Agents

Create these files only when the phase instructs you to do so. Do not create the complete tree in Phase 00 unless explicitly requested.
