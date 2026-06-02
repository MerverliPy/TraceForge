# Phase 00 — Repository Foundation

## Objective

Convert this planning-only repository into a valid TypeScript project foundation without implementing TraceForge runtime behavior.

## Scope

Create only project infrastructure needed for future phases.

## Allowed Work

- Initialize package metadata
- Add TypeScript configuration
- Add lint/test/build tooling
- Add placeholder directories if needed
- Add environment example
- Add contributor scripts
- Add CI workflow if not already present
- Add basic smoke test placeholder that validates project setup only

## Explicitly Out of Scope

- No agent runtime
- No CLI behavior
- No TUI behavior
- No model adapters
- No tools
- No memory implementation
- No orchestration implementation

## Expected Files to Create or Update

- `package.json`
- `pnpm-lock.yaml`
- `tsconfig.json`
- `vitest.config.ts`
- `.gitignore`
- `.env.example`
- `.github/workflows/ci.yml`
- possibly `tests/smoke/project-setup.test.ts`

## Suggested Dependencies

Use only foundation dependencies:

- TypeScript
- Vitest
- tsx or equivalent TypeScript runner
- ESLint/Prettier if desired

Do not add model provider SDKs yet.

## Acceptance Criteria

- `pnpm install` works.
- `pnpm typecheck` works.
- `pnpm test` works.
- `pnpm build` works or has a deliberately minimal no-runtime build.
- No TraceForge runtime implementation exists yet.
- README still clearly says implementation begins phase-by-phase.

## Validation Commands

```bash
pnpm install
pnpm typecheck
pnpm test
pnpm build
```

## Completion Report Required

Use the format in `AGENTS.md`.
