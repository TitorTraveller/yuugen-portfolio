# Gift a roll

**Status:** idea, to explore · Priority: not scheduled (outside Phases 0–4) · Added: 2026-11-23

## Idea

Let Matías shoot a whole roll for one specific person and give it to them as a gift, the way you would hand over a film roll, but digitally.

It comes from wanting to give rolls to people you can't hand them to in person: someone you don't know yet, someone far away, or someone you want to give something to for a personal reason. Physically that's impossible; a link isn't.

## Flow

1. **Load the roll:** Matías creates a roll with a fixed number of exposures (24 or 36, like film), the recipient's name and an optional dedication.
2. **Shoot:** he adds photos to the roll over days or weeks. The counter shows the exposures left (`12/36`). The recipient sees nothing yet.
3. **Finish the roll:** when the counter reaches the end, or he closes it early. From then on no photos can be added, as with film.
4. **Deliver the link:** the roll gets its own link. It can go in a message, or as a QR code on a printed card or inside an empty film canister, which brings back part of the physical gesture. *(To keep exploring.)*
5. **Wait:** if the recipient opens the link before the roll is developed, they see a "your roll is being developed" state instead of an error.
6. **Develop:** Matías edits the photos, writes the alt text and marks the roll as developed.
7. **Open the gift:** the recipient sees the photos, with a "reveal" moment the first time, and can download them.

Roll states: `loading → shooting → finished → developing → developed`. Optional: `revoked`.

## Evaluation: can the roll be shared independently?

The question has two parts.

### 1. Can the recipient pass the roll on to someone else?

**Option A · The link is the key (capability URL).** An unguessable URL (`/roll/<random-token>`): whoever has it can see the roll, without accounts.
- ✅ Zero friction; it works like a physical gift: once it's given, it belongs to the recipient, and they can show it to whoever they want.
- ✅ Simple to build: no login, no recipient email to store.
- ⚠️ If the link leaks, anyone can see it. Mitigations: a long random token, `noindex`, the roll never listed anywhere, and Matías can revoke it or create a new link.

**Option B · Personal access.** Link plus a code sent separately, or the recipient signs in with their email (a magic link).
- ✅ More private: only that person can open it.
- ⚠️ More friction, and it breaks the "someone I don't know" case: you need their email or a second channel.
- ⚠️ Storing emails means handling personal data, with the privacy obligations that come with it.

**Leaning:** A for a first version, since it fits the gift metaphor, plus revocation. B only if a real case calls for more privacy.

### 2. Is the roll independent from the portfolio?

- A gift roll is **private by default**: it doesn't appear in `/photo` and doesn't count as public content.
- If Matías later wants to publish photos from it in the gallery, that's a separate, explicit action. If the recipient is in the photos, ask them first.
- The roll page can share the site's visual identity (see `visual-identity.md`) but should feel like its own object, closer to an envelope than to a gallery page.

## Constraints

- **Privacy:** photos of people are personal data. Private rolls must not leak through search engines, the sitemap, image URLs or Open Graph previews (no preview image in the link unless Matías chooses one).
- **Accessibility (WCAG 2.2 AA):** alt text is written during "developing", before delivery. The reveal animation respects `prefers-reduced-motion`. The waiting state is real text, not just an animation.
- **Images:** originals in private storage, served through the roll's access check, not as public `public/` files.

## What it needs (why it's not for now)

This is the first feature that needs a **backend**: private storage, roll data, an admin area where Matías can sign in, and access checks. Today the site is static content. It fits after Phase 2 or as a Lab piece (Phase 3), and it would make a strong dev case study for "behind the photo".

## Open questions

- Does Matías shoot on film and scan the photos, or shoot digitally with "roll" rules? It changes what "developing" means.
- Can the recipient download the originals, or only see them?
- Does the link expire, or does the gift last forever?
- Should the recipient be able to answer (a thank-you note), or is it one-way?
- Can a roll be given to several people, each with their own link?

## Next step

Answer the open questions, especially film vs digital and download, and sketch the recipient's screens (waiting and developed) before thinking about the backend.
