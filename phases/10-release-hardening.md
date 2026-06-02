# Phase 10 — Release Hardening

## Objective

Prepare TraceForge for an initial public alpha release.

## Scope

Focus on reliability, documentation, security posture, and contributor readiness.

## Required Work

- Complete README quickstart
- Complete architecture docs
- Complete security docs
- Add release checklist
- Ensure CI validates lint/typecheck/test/build
- Add example traces
- Add benchmark baseline
- Tag issues for roadmap
- Review dependency licenses
- Review secret redaction

## Expected Files

- README updates
- `docs/release-checklist.md`
- `docs/examples.md`
- `.github/workflows/ci.yml` updates if needed
- Additional tests

## Out of Scope

- No hosted docs site unless trivial
- No plugin marketplace
- No major architecture rewrite

## Acceptance Criteria

- New user can clone and run MVP.
- New contributor can understand architecture.
- Security policy exists and matches implementation.
- CI passes.
- Benchmarks have baseline output.
- Release checklist is complete.

## Validation Commands

```bash
pnpm lint
pnpm typecheck
pnpm test
pnpm build
pnpm benchmark
```
