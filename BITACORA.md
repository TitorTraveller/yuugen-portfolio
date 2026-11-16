# Bitácora

Short log of what got done, newest first.

## 2026-11-16

- Vercel connected to GitHub: preview deployment per PR, production on merge to `main`.
- Vitest + Testing Library + CI (lint, typecheck, tests) merged in #1.
- `@types/node` bumped to `^24`: Vitest 5 requires `^22 || >=24` as a peer dependency.
- `typecheck` runs `next typegen` first, because route types like `LayoutProps` are generated and don't exist on a clean CI runner. See [decision 0001](docs/decisiones/0001-next-typegen-before-tsc.md).

## 2026-11-12

- Repo renamed to `yuugen-portfolio`.
- `CLAUDE.md` published in English, without personal details (single file, so there's no second version to keep in sync).
