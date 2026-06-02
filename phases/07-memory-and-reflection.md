# Phase 07 — Memory and Reflection

## Objective

Add local memory, run summarization, retrieval, and self-critique/reflection.

## Scope

Implement local memory without external vector database infrastructure.

## Required Work

- SQLite store
- Run summary records
- Reflection records
- Full-text retrieval
- Memory query before planning
- Reflection after run completion
- Memory write after completion
- Tests with temporary database

## Expected Files

- `src/memory/sqlite.ts`
- `src/memory/retrieval.ts`
- `src/memory/compression.ts`
- `src/memory/reflections.ts`
- `src/improvement/self-critique.ts`
- Tests

## Out of Scope

- No embedding/vector database
- No persistent cloud memory
- No background learning job

## Acceptance Criteria

- Completed runs produce summaries.
- Reflections are stored.
- New tasks can retrieve relevant prior summaries/reflections.
- Memory events are emitted.
- Tests prove insert, retrieval, deletion, and redaction behavior.

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
