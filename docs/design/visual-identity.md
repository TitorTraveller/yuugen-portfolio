# Visual identity

Ideas and decisions for the site's visual identity: type, color, imagery and tone. Each idea gets its own section with a status. Nothing here is decided until it says so.

The identity must serve the product direction: **photography first**, artistic, and never "developer who also takes photos" (see `docs/decisiones/0002-photography-first.md`).

---

## Idea: death / brutal death metal references

**Status:** idea, to explore · Added: 2026-11-23

Use the visual language of death metal, brutal death metal and related genres (grindcore, black metal, doom) to build a recognizable identity, as a complement to the photography rather than a replacement for it.

### What it could include

- **Lettering:** a logotype for "Matías Berríos" inspired by death metal band logos: symmetry, thorns, roots and branches, drips, sharp terminals. Hand-drawn or vectorized, used as an SVG.
- **Color:** a mostly black and dark-gray base, bone or off-white for text, and one restrained accent (dried-blood red, rust or toxic green). The photos keep their own color; the palette frames them.
- **Imagery and texture:** references to album art, xerox zine flyers, photocopy grain, high-contrast black and white, rough cutouts. It can echo the film side of the site (grain, scratches, light leaks).
- **Typography for reading:** the extreme lettering is display-only. Body text, navigation and captions use a readable typeface.

### Why it could work

- It gives the site a personal, memorable identity that a generic portfolio template doesn't have.
- It fits a photography-first, artistic site better than a clean "tech" look.
- It also works as a dev showcase: an SVG logotype, textures and animations are frontend work worth documenting in "behind the photo".

### Constraints (WCAG 2.2 AA and product)

- **The logo is never the only source of text.** Unreadable lettering needs a real text equivalent: an `<h1>` with the name (visually hidden if needed) or `aria-label` / `<title>` on the SVG (WCAG 1.1.1). Search engines and screen readers must still get "Matías Berríos".
- **Contrast:** text and focus indicators at 4.5:1 at least (3:1 for large text and UI components) on dark backgrounds and over textures (WCAG 1.4.3, 1.4.11). A red accent on black usually fails for body text, so use it for decoration or large type only, and measure it.
- **Readability over atmosphere:** no distressed or blackletter fonts in paragraphs, navigation or buttons.
- **Motion:** drips, glitches or flicker must respect `prefers-reduced-motion`, and nothing may flash more than 3 times per second (WCAG 2.3.1).
- **The photos come first:** the identity frames the photos and must not compete with them. Textures and lettering stay out of the gallery area.
- **The `/dev` door:** a recruiter coming from a CV must still understand where they are within seconds. The identity can be stronger on `/` and `/photo` and quieter on `/dev`, but it should feel like the same site.
- **Performance:** textures as optimized images or CSS/SVG, not heavy files on every page. The logo inline as SVG.

### Open questions

- How strong should it be: a full aesthetic, or touches (logo plus palette) over a sober base?
- Who draws the logo: Matías by hand, a commission, or an SVG built in code (it could be a Lab piece)?
- Does it connect to the "roll" metaphor and the entry animations (#7)? For example, the Photo roll could be analog and grainy and the Dev roll terminal-like, both in the same palette.
- References to collect: logos, album covers and flyers Matías likes, kept in a moodboard before any design work.

### Next step

Collect a moodboard (5–10 references) and decide how strong the identity should be. Then propose design tokens (colors, fonts) for `@theme` in the global CSS.
