# 0002 · Photography first, dev discovered from it

Date: 2026-11-17

## Context

The site was planned as a developer portfolio with a photography section. That made it read as "developer who also takes photos", which isn't the identity it should have. The site should be a photography portfolio that is also a dev portfolio. The audience includes recruiters in a hurry, who need to find the dev work fast.

## Decision

Combine three pieces:

1. **Entry roll choice:** on arrival the visitor picks which roll to load, Photo or Dev, each with its own animation. Details in `docs/design/entry-roll-choice.md`.
2. **Behind the photo:** a discreet layer on photos and gallery features shows how they're built. The site itself is the main dev case study.
3. **Direct door:** `/dev` is always one click away (footer or colophon) and works as a direct link for a CV.

## Consequences

- The gallery moves from Phase 2 to Phase 1, and the MDX case studies move to Phase 2.
- The "Home · Work · Photography · Lab" nav is dropped. Navigation is designed for each roll.
- The dev side doesn't depend on side projects. It grows with the site.

## Alternatives rejected

- **Door only (no behind-the-photo layer):** simpler, but photography and code would live side by side without ever touching.
- **Featuring existing side projects:** they're too small to represent the work well.
