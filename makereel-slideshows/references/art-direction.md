# Art direction

Use this before drafting Scratch scenes or reviewing Social text, so the plan presented for approval is worth approving. It decides what goes on each slide; the command contract and approval gates stay in the skill.

## Frame the deck

- **Job** — what the viewer should feel, learn or do after the last slide.
- **Audience and language** — write in the audience's language and register, not a translation.
- **Archetype** — choose one from [deck recipes](deck-recipes.md): listicle, mistakes, steps, story/transformation, myth vs fact, comparison, POV/relatable, soft plug. The archetype sets the beat order.
- **Length** — usually 5–8 slides; every slide must earn the swipe. Say why when you go longer.
- **Social** — keep the source deck's beat structure and write new copy according to the chosen copy mode.

## Write the arc

An arc, not a list: a hook that earns the swipe, body beats that pay it off, and a closer.

- **Hook (slide 1)** — 3–8 words, specific and true. Styles: curiosity gap, contrarian claim, specific number, mistake callout, POV/identity, before/after, question. Offer 2–3 hook options when the brief leaves room.
- **Body** — one idea per slide. A heading of 3–8 words carries the beat; add one supporting sentence (8–20 words) only when a fact, reason or step needs it. Never restate the heading in the body.
- **Closer** — payoff or summary, then one CTA: save, follow, comment prompt, or the single soft plug.
- **Plug** — at most one product mention per deck, in a peer-recommendation voice ("what finally worked for me"), never "buy now" or "click the link".
- **Density** — quick beats (hook, reveal, punchline, CTA) stay short; explanatory beats may use a full sentence. An explicit user constraint ("under 10 words") wins exactly. If copy does not fit, rewrite or split it across slides; never shrink type into illegibility.
- **Caption** — 1–3 lines that extend the hook, plus a question or CTA and a few relevant hashtags.

Ground every claim in the brief, website facts or user-supplied proof. No invented statistics, testimonials or results.

## Cast the images

Judge each candidate with the camera-roll test: could a real person have taken it?

- **Yes:** candid, mid-action subjects who ignore the camera, natural or phone-flash light, lived-in imperfect settings, visible texture.
- **No, on sight:** baked-in text or designed layouts, stock posing at the lens, logos or watermarks (check the corners), pixelation, waxy over-perfect renders.
- One distinct scene per slide; vary framing (wide, mid, close, hands) and setting across the deck while keeping one color/light family.
- The image carries the mood; the text carries the meaning. Pick images that leave calm space where text will sit.
- For a recurring persona, load the **avatars** skill.

## Lay out each Scratch slide

Use [layout recipes](layout-recipes.md) for full-bleed, split, grid and image-over-card layouts with validated coordinates.

- Keep all text inside the safe area: clear of the top ~200 px, the bottom ~420 px, and the right ~140 px from mid-height down (TikTok's header, caption and action rail).
- Contrast first: light text on a solid text background, dark text on a light card, or a stroke/shadow when the photo area behind the text is calm and even. Colors are `#RRGGBB` only (no alpha).
- Type scale at 1080 wide: hook 80–96, headings 64–80, body 44–56, labels 36–40. Headings at weight 700–800, body 400–500.
- One font family per deck (two at most), consistent alignment, consistent block positions between slides of the same kind.
- Mark the first-slide hook `textRole: "hook-text"`; other text `content-text`. Use `textKind` `headline` or `paragraph`.
- Do not cover faces or the product with text; move the block or choose another image.

## Self-review before presenting

- Does slide 1 make sense with no context, and would you swipe?
- Does each slide do one job, and does the order build?
- Any text outside the safe area, low contrast, over a face, or overflowing its box?
- Same claim twice? Any claim without a source?
- Is the plug (if any) single and soft, with exactly one CTA at the end?

## Variants (A/B)

A variant is a second, separately approved carousel that changes one variable: the hook, the first image, slide count, copy mode (Social), or Avatar vs no Avatar. Keep everything else identical and label both decks with the variable.

## Improve an existing draft

Read it with `makereel carousel get ID`, critique it against this guide, and propose specific edits. The CLI creates new drafts and cannot edit an existing one, so offer edits the user makes in the editor or a new approved draft; never overwrite or delete their work.
