# Analog neon lighting

**Status:** idea, to explore · Priority: not scheduled · Added: 2026-11-23

Nothing here is decided. It's one possible direction for the site's visual identity (see `visual-identity.md`).

## Idea

Use analog neon-style lighting as part of the site's visual language: colors, outlines, blurs and possibly other visual effects.

## What it could include

To explore, not a list to implement:

- **Color:** a dark base with a few light colors. Starting points: gas-tube red-orange, cyan, magenta, darkroom safelight red.
- **Outlines:** thin, tube-like strokes around links, titles or frames. Candidates: `border`, `box-shadow`, SVG `stroke`.
- **Blurs:** soft halos and light spilling onto the background. Candidates: layered `text-shadow`, `filter: blur()`, radial gradients.
- **Possible effects:** a tube switching on, halation (the red glow around highlights on film), light leaks, grain, slight color misalignment.

"Analog" is what should set it apart from generic cyberpunk: imperfect, warm light that looks photographed on film, rather than clean digital glow.

## Constraints

- **Photos first:** colored light changes how a photo's color is perceived. Keep the glow away from the gallery photos.
- **Contrast (WCAG 1.4.3, 1.4.11):** 4.5:1 for text (3:1 for large text), and 3:1 for UI components. Measure the solid text color against the background, without counting the halo.
- **Focus (WCAG 2.4.7, 1.4.11):** focus needs a solid outline, not only a glow. It must also look different from decorative outlines.
- **Forced colors:** `box-shadow` and `text-shadow` are removed in forced-colors mode, so nothing can depend on them.
- **Motion (WCAG 2.3.1, 2.2.2):** no more than 3 flashes per second. Looping flicker that lasts over 5 seconds needs a way to pause it. Respect `prefers-reduced-motion` with a steady light.
- **Performance:** large blurs and animated shadows are expensive to paint. Prefer static glows and animate `opacity`. Test on a mid-range phone.

## Relation to other ideas

- **Death metal references (`visual-identity.md`):** both share a dark base, but that idea proposes one restrained accent and neon suggests several. They need one shared palette.
- **Entry roll choice (`entry-roll-choice.md`):** Photo and Dev could each have their own light color. Text still has to tell them apart, not color alone (WCAG 1.4.1).

## Open questions

- Is neon the main language, or an accent for a few moments such as the entry screen?
- Does it combine with the death metal direction, or are they alternatives?
- Which colors, and how many?
- Does the reference come from neon signs, darkroom light, or Matías's own night photos?

## Next step

Collect 5–10 references (including Matías's own photos, if any fit) alongside the death metal moodboard, then compare both directions before choosing colors.
