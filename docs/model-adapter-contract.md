# Model Adapter Contract

## Goal

TraceForge should support multiple model providers behind a stable runtime contract.

## Planned Providers

| Provider | MVP Status |
|---|---|
| OpenAI | Required |
| Anthropic | Required |
| Ollama | Required |
| LiteLLM | Optional later |

## Adapter Responsibilities

A model adapter should handle:

- Provider configuration
- Model selection
- Prompt/message formatting
- Streaming if supported
- Tool call translation if supported
- Token/cost metadata if available
- Error normalization
- Trace event emission boundaries

## Core Adapter Boundary

The orchestration layer should not know provider-specific request shapes. It should use a normalized call contract.

## Required Events

- `model.request.started`
- `model.stream.delta`
- `model.request.completed`
- `model.request.failed`

## MVP Rule

Do not optimize for every provider at once. Implement the smallest common denominator first:

- text input
- text output
- metadata
- timeout
- cancellation later
