# Entry choice: "which roll do you want to load?"

**Priority: High** · Status: to be designed · Added: 2026-11-17

Keep this in mind when designing the UX, the UI and the architecture.

## Idea

On arrival, the visitor chooses which "roll" to load:

- **Photo**: the photography portfolio.
- **Dev**: the development portfolio.

Each option has its own animation, matching its style.

## Why

- A recruiter in a hurry gets to the dev portfolio on the first screen, with no hunting.
- Someone who came for the photography goes straight to it.
- The film-roll metaphor ties the two sides together from the very first interaction.

## Things to consider

**UX**

- The choice must not become a wall. Direct links (`/dev`, a photo or series URL) skip it and land on the content. This is the URL you'd put in a CV.
- Decide whether to remember the choice on the next visit, and how to switch to the other roll from anywhere in the site.
- Keep it short: one screen with two clear options, and no loading time before the content.

**UI and animation**

- **Pending:** the animation concepts aren't defined yet. Build the static version first. It's needed anyway for `prefers-reduced-motion`.
- Two animation styles: photo (analog, film) and dev (code, technical). They have to be different, but feel like they belong to the same site.
- Respect `prefers-reduced-motion`: without animation, the choice still works and makes sense (WCAG 2.3.3).
- If an animation lasts more than 5 seconds or loops, it needs a way to pause or skip it (WCAG 2.2.2).

**Accessibility**

- Both options are real links (`<a href>`), reachable by keyboard and with visible focus. Don't use clickable `div`s.
- The text says what each option is ("Photography", "Development"), not just the metaphor.

**Architecture**

- **Decided (2026-11-17): routes.**

  ```
  /              Entry choice: Photo · Dev
  /photo         Gallery (and /photo/[series])
  /dev           Dev side (and /dev/[case-study])
  ```

  Each roll has its own `layout.tsx`, with its own navigation and style. The choice is two plain links. It's not remembered for now: `/` shows it on every visit. Add that only if it becomes annoying.
  Rejected: gallery at `/` with a first-visit overlay. It needs a cookie, and it's close to the "wall" this doc wants to avoid.
- Each roll is a route with its own URL, not state that lives only in JavaScript. That keeps it shareable, indexable and working without JS.
- The animations go in client components. The rest of the page stays a Server Component.
- Open question: the site-wide navigation changes depending on the roll (Photo vs. Dev). Define it together with this screen.

## Relation to other decisions

- It complements the "behind the photo" layer (option B): this screen solves the problem of the recruiter in a hurry, so the layer can stay discreet.
- It replaces the "Home · Work · Photography · Lab" nav proposed earlier, which is on hold.
