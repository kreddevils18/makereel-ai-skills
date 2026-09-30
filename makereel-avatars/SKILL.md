---
name: avatars
description: Set up and use Makereel Avatars — private character collections that keep one recurring persona consistent across carousels. Use to define a persona, choose or prepare the persona's photos, bind an Avatar to Social image slots, mention it as @Avatar context, or keep a Scratch deck on one face. Triggers include "avatar", "nhân vật", "persona", "character collection", "same person on every slide", "rotate my model photos". Chains as avatars → slideshows → generate. Not for AI face generation, face swaps, identity-model training, or depicting real people without their consent.
argument-hint: "[persona or avatar name]"
metadata:
  version: "2.3.0"
---

# Makereel Avatars

In Makereel an **Avatar** is a private **character collection**: a set of the user's own images of one persona. Makereel does not generate faces. It gives the persona three jobs:

1. **Social image slots** — an image binding with `kind: "character"` fills a slot from the Avatar's members in order, continuing after `previousAssetId` when supplied, so a deck or a series rotates through the persona's photos.
2. **Adaptation context** — `contextReferences` rows `{kind: "avatar", id}` (the web Social brief's `@Avatar` mention) tell the copy adaptation who is speaking. Context references are not image bindings.
3. **Learning** — when a posted carousel is linked, Makereel records which characters it referenced, so campaigns can compare Avatar-led posts with others.

Orient a new user in one sentence: an Avatar is a set of photos of one persona that you choose; Makereel reuses them consistently but does not create new faces.

Bootstrap as the **generate** skill describes. Everything below except uploads and imports is read-only.

## Split identity from scene

Keep what stays constant separate from what changes per slide.

- **Identity (persona sheet)** — name, age band, look, signature wardrobe and colors, setting family (home, gym, office), voice and vocabulary, niche, topics they never speak about. Draft it with the user and suggest pasting a short version into the collection description in the web app (up to 2000 characters) so it travels with the Avatar.
- **Scene (per slide)** — the moment, pose, light and caption. Choose it from the Avatar's existing photos; never promise a pose or expression that no member shows.

Use a consistent persona name in copy and captions. Do not attach invented credentials, results or testimonials to the persona.

## Find an existing Avatar

The CLI and MCP tools do not list collections or their kind. To resolve an Avatar:

1. Ask the user which Avatar to use. Its ID is the last segment of its Library link, `/dashboard/library/collections/<id>`.
2. If they do not have the link, run `makereel assets list` (paginate; keep `--unpacked` off), group assets by `collectionId`, and show a few recognizable images from each candidate group with `assets get ID`. Let the user confirm which group is the Avatar. An asset's `collectionId` does not tell you whether that collection is a character collection; the user must confirm.
3. Inspect members visually when the runtime can. Note gaps: missing angles, settings, expressions, or photos with baked-in text.

A Social `character` binding fails if the referenced collection is not a character collection. Report that failure honestly and ask the user to check the collection type; do not switch to a standard collection silently.

## Create or extend an Avatar

Creating the collection and adding members happens in the Makereel web app:

1. Gather the persona's photos per [the Avatar photo guide](references/avatar-photo-guide.md), including consent and rights.
2. Photos already in the Library need no upload. For new local files, list the exact files and get explicit approval, then run `makereel assets upload FILE` for each (PNG, JPEG or WebP up to 10 MiB). For user-supplied public Pinterest Pin URLs, use `makereel assets import-pinterest URL` after the same approval. A failed upload does not authorize a substitute.
3. Tell the user to open **Library → Assets**, create a collection, choose **Character collection**, name it after the persona, and add the approved images. Membership is many-to-many; adding images to an Avatar does not delete them elsewhere.
4. Ask for the new collection link, then read the members back through `assets list` to confirm the Avatar is ready.

Never create an Avatar of a real person without that person's documented consent, and never of a minor or a public figure.

## Use an Avatar in a carousel

**Social** (remix a TikTok URL or Viral Post): for every image slot the persona should fill, add a binding row, and optionally mention the Avatar as context:

```json
[
  { "slidePosition": 0, "elementId": "IMAGE_ELEMENT_ID", "kind": "character", "collectionId": "AVATAR_COLLECTION_ID" }
]
```

```json
[{ "kind": "avatar", "id": "AVATAR_COLLECTION_ID" }]
```

The first file goes to `--image-bindings`; the second to `--context-references` (MCP `contextReferences`). Bind product or scenery slots to other assets or collections. Everything else — analysis approval, reviewed slides, copy mode, plan approval — follows **generate**.

**Scratch**: scenes need explicit `assetId` values, so pick specific members of the Avatar with `assets get` and place them. Use a distinct photo per slide unless repetition is deliberate, and keep wardrobe and setting coherent across the deck.

Before presenting any plan, run the consistency check:

- Same person on every persona slide; no stray faces from other collections.
- Wardrobe, setting family and light feel like one camera roll.
- Copy sounds like the persona sheet, in first person when the persona is the narrator.
- Text does not cover the face; move the text block or choose another member.

## Deliver

Report the Avatar's name, member count, the gaps you noticed, and exactly where it is used in the plan (slots bound, context mentioned). Carousel creation, scheduling and delivery links follow **generate**.
