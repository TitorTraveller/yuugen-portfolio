# CLAUDE.md · Photography + Dev Portfolio

Personal site of Matías Berríos: a photography portfolio first, which is also his frontend developer portfolio. Visitors come for the photos and discover that the site itself is the dev work.

## Product direction

- **Photography first.** The site's look and feel is artistic. It must not read as "developer who also takes photos".
- **Entry choice (high priority):** the visitor picks which "roll" to load, Photo or Dev, each with its own animation. See `docs/design/entry-roll-choice.md` before any work on the home page, routes, navigation or animations.
- **Behind the photo:** each photo and gallery feature has a discreet layer showing how it's built (shot data, image delivery, accessibility decisions). The site is the main dev case study.
- **Direct door to dev:** `/dev` is always reachable with one click (footer or colophon) and works as a direct link for a CV.
- Rationale: `docs/decisiones/0002-photography-first.md`.

## Working mode (Augmented Coding)

- Claude proposes, Matías integrates by hand.
- One step at a time. Snippets of up to ~80 lines, explaining the why and naming any new concept.
- Don't write large files or several features at once unless asked.
- Simplest thing that works: no abstractions, patterns or files the task doesn't call for.
- Alternatives: 2 at most, each with its trade-off. Matías decides.
- If you spot a bug in his code, say so directly. If he corrects yours, adjust.
- Reply in Spanish (Chile); code, names and commits in English.

## Work tracking

Work state lives on GitHub, not in conversation memory.

- **Session start:** run `gh issue list` and check the current milestone before proposing work. Issues labeled `priority: high` go first.
- **Board:** GitHub Project "Yuugen Portfolio" (Todo · In Progress · Done), linked to this repo.
- **Milestones = phases.** Every issue in the current phase belongs to its milestone.
- **Where things go:** issues = what to do · PRs = how it was done, plus evidence (CI, Vercel preview) · `docs/decisiones/` = why · `BITACORA.md` = what happened and when.
- **Closing:** a PR that implements an issue says `Closes #<n>` in its description. A PR that only documents an idea doesn't.

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

- Content: MDX files in `content/` with frontmatter, loaded with `next-mdx-remote` (Phase 2)
- Lab: native TypeScript with no runtime dependencies, mounted as islands (Phase 3)
- Playwright + axe for e2e and accessibility, Storybook and Lighthouse CI (Phase 4)

## Phases

0. **Foundation:** done (tests, CI, Vercel previews, protected `main`).
1. **Experience and gallery:** entry roll choice, photo gallery, navigation for each roll. Design before code.
2. **Dev side:** `/dev`, MDX case studies (starting with the site itself), "behind the photo" layer.
3. **Lab:** tools, once there's something worth showing.
4. **Quality:** e2e, accessibility audits, Storybook, Lighthouse CI.

Not yet:

- **Gallery layout:** being designed in Phase 1. Don't assume a layout, lightbox or data structure until the design is agreed.
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
- Non-obvious decisions → short note in `docs/decisiones/`. Design explorations → `docs/design/`.
- When closing a task, suggest 1–3 lines for `BITACORA.md`.

## Structure

To be documented when Phase 1 is defined.
