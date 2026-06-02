# Phase 04 — Model Adapter Layer

## Objective

Implement provider-independent model adapter infrastructure and first provider adapters.

## Scope

Add model adapter interface, registry, config, and initial providers.

## Required Providers

- OpenAI
- Anthropic
- Ollama

## Required Work

- Define `ModelAdapter` contract
- Implement adapter registry
- Normalize text request/response
- Emit model trace events
- Add timeout/error normalization
- Add tests with mocked providers

## Expected Files

- `src/models/base.ts`
- `src/models/registry.ts`
- `src/models/openai.ts`
- `src/models/anthropic.ts`
- `src/models/ollama.ts`
- Tests using mocks/fakes

## Out of Scope

- No tool-call translation yet unless minimal provider shape requires it
- No streaming requirement unless easy to isolate
- No orchestration loop

## Acceptance Criteria

- Core runtime can call a provider through the normalized interface.
- Provider errors normalize to TraceForge errors.
- Model calls emit trace events.
- Tests do not require real API keys.

## Validation Commands

```bash
pnpm typecheck
pnpm test
```
