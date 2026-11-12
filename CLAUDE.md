# CLAUDE.md · Dev + Photography Portfolio

Personal site of Matías Berríos: frontend developer portfolio + photography gallery + tools Lab.

## Working mode (Augmented Coding)

- Claude proposes, Matías integrates by hand.
- One step at a time. Snippets of up to ~80 lines, explaining the why and naming any new concept.
- Don't write large files or several features at once unless asked.
- Simplest thing that works: no abstractions, patterns or files the task doesn't call for.
- Alternatives: 2 at most, each with its trade-off. Matías decides.
- If you spot a bug in his code, say so directly. If he corrects yours, adjust.
- Reply in Spanish (Chile); code, names and commits in English.

## Stack

Confirmed:

- Next.js (App Router) + React + TypeScript (`strict`, no `any`)
- Tailwind CSS v4: tokens in `@theme` inside the global CSS; utilities in the JSX; `clsx` only when a component has variants. No component libraries.
- ESLint + `tsc` for linting and types
- Vitest + Testing Library for unit and component tests (from Phase 0)
- GitHub Actions: lint, typecheck and tests on every PR
- Deploy on Vercel, with a preview per PR
- WCAG 2.2 AA from day one

Proposed (confirmed when each phase starts):

- Content: MDX for case studies (Phase 1)
- Lab: native TypeScript with no runtime dependencies, mounted as islands (Phase 3)
- Playwright + axe for e2e and accessibility, Storybook and Lighthouse CI (Phase 4)

Not yet:

- **Gallery:** shape and design undefined; explored in Phase 2. Don't assume a layout, lightbox or data structure.
- **Image pipeline with `sharp`:** postponed. Use `next/image` in the meantime.

## Commands

- `npm run dev`
- `npm run build`
- `npm run lint`
- `npm run typecheck`
- `npm test`

## Conventions

- Conventional Commits (`feat:`, `fix:`, `docs:`, `test:`, `refactor:`, `chore:`).
- Branches `feat/<task>`; small PRs, one per issue.
- Accessibility WCAG 2.2 AA at minimum: keyboard navigation, visible focus, alt text on every photo.
- Non-obvious decisions → short note in `docs/decisiones/`.
- When closing a task, suggest 1–3 lines for `BITACORA.md`.

## Structure

To be documented when Phase 1 is defined.
