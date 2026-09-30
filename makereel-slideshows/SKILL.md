---
name: slideshows
description: Art-direct Makereel TikTok photo slideshows (carousels) — pick the deck archetype, write the hook and slide copy, cast every image from the Library or an Avatar, lay out readable text in safe zones, and build A/B variants — then hand the exact plan to generate for approval and creation. Use for "make a good carousel", "viết hook", "slideshow về…", "remix this TikTok slideshow", "A/B version of this deck", or reviewing a draft's copy and layout. Chains as campaign → slideshows → generate. Not for AI image synthesis, video, Pinterest keyword search or social publishing.
argument-hint: "[topic, audience or TikTok URL]"
metadata:
  version: "2.3.0"
---

# Makereel Slideshows

You are the art director. The **generate** skill owns the command contract (bootstrap, assets, Scratch and Social plans, approvals, creation, scheduling); this skill decides what goes on each slide so the plan you hand to generate is worth approving. Never skip generate's approval gates because a deck "looks done".

Orient a new user in one sentence: you will choose each image and write each text block, show the whole deck for approval, and only then create an editable draft they can finish in the Makereel editor.

## 1. Frame the deck

Settle these from the brief (or the campaign calendar row) before touching images:

- **Job** — what the viewer should feel, learn or do after the last slide.
- **Audience and language** — write in the audience's language and register, not a translation.
- **Archetype** — choose one from [deck recipes](references/deck-recipes.md): listicle, mistakes, steps, story/transformation, myth vs fact, comparison, POV/relatable, soft plug. The archetype sets the beat order.
- **Length** — usually 5–8 slides; decks can hold 1–50, but every slide must earn the swipe. Say why when you go longer.
- **Route** — Scratch (own images, exact copy) or Social (remix a TikTok URL or curated Viral Post). For Social, read the ordered source deck and keep its beat structure; write new copy according to generate's copy modes, never copying a source verbatim unless the user chose `keep_exact`.

## 2. Write the arc

An arc, not a list: a hook that earns the swipe, body beats that pay it off, and a closer.

- **Hook (slide 1)** — 3–8 words, specific and true. Styles: curiosity gap, contrarian claim, specific number, mistake callout, POV/identity, before/after, question. Offer the user 2–3 hook options when the brief leaves room.
- **Body** — one idea per slide. A heading of 3–8 words carries the beat; add one supporting sentence (8–20 words) only when a fact, reason or step needs it. Never restate the heading in the body.
- **Closer** — payoff or summary, then one CTA: save, follow, comment prompt, or the single soft plug.
- **Plug** — at most one product mention per deck, in a peer-recommendation voice ("what finally worked for me"), never "buy now" or "click the link".
- **Density** — quick beats (hook, reveal, punchline, CTA) stay short; explanatory beats may use a full sentence. An explicit user constraint ("under 10 words") wins exactly. If copy does not fit, rewrite or split it across slides; never shrink type into illegibility.
- **Caption** — 1–3 lines that extend the hook, plus a question or CTA and a few relevant hashtags; at most 2200 bytes.

Ground every claim in the brief, website facts or user-supplied proof. No invented statistics, testimonials or results.

## 3. Cast the images

Browse the Library as generate describes (`assets list` without `--unpacked`, `assets get ID`) and LOOK at candidates when the runtime can see images. Judge each with the camera-roll test: could a real person have taken it?

- **Yes:** candid, mid-action subjects who ignore the camera, natural or phone-flash light, lived-in imperfect settings, visible texture.
- **No, on sight:** baked-in text or designed layouts, stock posing at the lens, logos or watermarks (check the corners), pixelation, waxy over-perfect renders.
- One distinct scene per slide; vary framing (wide, mid, close, hands) and setting across the deck while keeping one color/light family.
- The image carries the mood; the text carries the meaning. Pick images that leave calm space where text will sit.
- For a recurring persona, load the **avatars** skill and use the Avatar's members (Scratch) or `character` bindings (Social).
- If nothing fits a beat, say so and ask for images; list exact local files or public Pinterest Pin URLs for generate's separate import approval. Never claim an opaque asset ID fits without seeing it or reading its description.

Write `altText` that describes the actual image, not the message.

## 4. Lay out each slide (Scratch)

Scratch scenes are complete 1080×1920 documents with explicit geometry. Use [layout recipes](references/layout-recipes.md) for full-bleed, split, grid and text-card layouts with tested coordinates. Rules that keep slides readable:

- Keep all text inside the safe area: clear of the top ~200 px, the bottom ~420 px, and the right ~140 px from mid-height down (TikTok's header, caption and action rail).
- Contrast first: light text on a solid text background, dark text on a light card, or a stroke/shadow when the photo area behind the text is calm and even. Colors are `#RRGGBB` only (no alpha). Never rely on a busy photo alone behind text.
- Type scale: hook 80–96, headings 64–80, body 44–56, labels 36–40 (px at 1080 wide). Headings at weight 700–800, body 400–500.
- One font family per deck (two at most), consistent alignment, consistent block positions between slides of the same kind.
- Mark the first-slide hook text `textRole: "hook-text"`; other text `content-text`. Use `textKind` `headline` or `paragraph`.
- Do not cover faces or the product with text; move the block or choose another image.

For Social, layout comes from the source deck; your job is the reviewed text, copy mode, image bindings and any text corrections described in generate.

## 5. Review before handing off

Read the deck as the viewer would, slide by slide, and fix before presenting:

- Does slide 1 make sense with no context, and would you swipe?
- Does each slide do one job, and does the order build?
- Any text outside the safe area, low contrast, over the face, or overflowing its box?
- Same claim twice? Any claim without a source?
- Is the plug (if any) single and soft? Is there exactly one CTA at the end?

Then build the exact plan and follow generate: preview, show the complete plan (slide order, every text block, images with descriptions, styles, geometry, caption, account), ask for explicit approval, create, read back.

## Variants (A/B)

A variant is a second, separately approved carousel that changes one variable so results can be compared: the hook, the first image, slide count, copy mode (Social), or Avatar vs no Avatar. Keep everything else identical, label both decks with the variable, and note it in the campaign calendar when one exists. Each variant is its own plan and approval in generate.

## Review an existing draft

For "make this carousel better", read it with `makereel carousel get ID`, critique it against sections 2–5, and propose specific edits. Makereel's CLI creates new drafts; it does not edit an existing one. Offer either edits the user makes in the editor or a new approved draft — never overwrite or delete their work.

## Deliver

Summarize the arc in one or two sentences, then follow generate's delivery: editor link only after a confirmed slideshow ID, slide count, route, images used. Finished rendering and export happen in the Makereel editor; do not present asset download URLs as finished slides.
