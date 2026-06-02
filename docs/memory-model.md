# Memory Model

## Goal

TraceForge memory should improve future runs without becoming opaque or infrastructure-heavy.

## MVP Storage Choice

Local SQLite with full-text retrieval is the planned default.

## Memory Types

| Type | Purpose |
|---|---|
| Run summary | Condensed record of completed run |
| Step summary | Condensed record of major step |
| Reflection | What failed, what worked, what to try next |
| Tool stat | Tool success/failure/latency history |
| Benchmark result | Performance and quality history |

## Retrieval Flow

```text
Incoming task
  → Normalize query text
  → Search run summaries and reflections
  → Rank results
  → Return compact context to planner
```

## Compression Flow

```text
Completed run
  → Collect plan, events, outputs, failures
  → Produce compact summary
  → Store summary and searchable text
```

## Safety Requirements

- Redact secrets before storing memory.
- Allow memory deletion by run id.
- Do not store raw shell output by default if it may contain secrets.
- Keep memory inspectable by humans.

## MVP Rule

Do not introduce embeddings or vector databases until benchmark evidence shows full-text retrieval is insufficient.
