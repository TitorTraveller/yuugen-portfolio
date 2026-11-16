# 0001 · Run `next typegen` before `tsc`

Date: 2026-11-16

## Context

Next.js 16 provides global types such as `LayoutProps` and `PageProps`, generated into `.next/types/` by `next dev` or `next build`. Locally that folder already exists, so `tsc --noEmit` passes. On a clean CI runner it doesn't, and typecheck fails with `Cannot find name 'LayoutProps'`.

## Decision

The `typecheck` script is `next typegen && tsc --noEmit`. `next typegen` generates only the type definitions, without a full build.

## Consequences

- Typecheck gives the same result locally and in CI, with or without `.next/`.
- It adds a few seconds per run.
- Alternative rejected: running `next build` before typecheck in CI. It works, but it's much slower and mixes two concerns in one step.
