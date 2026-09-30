# Layout recipes (Scratch, 1080×1920)

Coordinates are pixels on the 1080×1920 canvas. Every scene needs 1, 2, 4 or 6 background images and at least one text block; each image element names an explicit `assetId`. Replace `ASSET_*` with approved asset IDs and the copy with approved text. Colors are `#RRGGBB`.

## Safe area

TikTok overlays the top header, the bottom caption and the right-side action rail. Keep text inside:

- `y` from 200 to 1500 (nothing in the top ~200 px or bottom ~420 px).
- `x` from 60 to 1020 above mid-height; from 60 to 940 below `y` 900, where the action rail sits.

Images may bleed to the edges; only text and key subjects need the safe area.

## Shared text styles

Reuse these across a deck and change only `text`, `geometry` and, rarely, `align`.

```json
{
  "hook":    { "fontFamily": "Outfit", "fontSize": 88, "fontWeight": 800, "fontStyle": "normal", "fill": "#ffffff", "align": "center", "background": { "color": "#111111", "paddingX": 28, "paddingY": 22, "cornerRadius": 18 } },
  "heading": { "fontFamily": "Outfit", "fontSize": 72, "fontWeight": 700, "fontStyle": "normal", "fill": "#ffffff", "align": "left",   "background": { "color": "#111111", "paddingX": 24, "paddingY": 20, "cornerRadius": 16 } },
  "body":    { "fontFamily": "Outfit", "fontSize": 50, "fontWeight": 500, "fontStyle": "normal", "fill": "#111111", "align": "left",   "background": { "color": "#ffffff", "paddingX": 24, "paddingY": 20, "cornerRadius": 16 } },
  "label":   { "fontFamily": "Outfit", "fontSize": 40, "fontWeight": 700, "fontStyle": "normal", "fill": "#ffffff", "align": "center", "stroke": { "color": "#000000", "width": 6 } }
}
```

Rough capacity at these sizes in a 900 px wide box: hook ≈ 16 characters per line, heading ≈ 20, body ≈ 32. Give each block a height of about `lines × fontSize × 1.3 + 2 × paddingY`, and shorten or split copy that would need more lines than the box allows.

## A. Full-bleed hook

One image fills the canvas; the hook sits in the upper third.

```json
{
  "scene": {
    "version": 1, "width": 1080, "height": 1920, "background": "#111111",
    "elements": [
      { "id": "bg", "type": "image", "geometry": { "x": 0, "y": 0, "width": 1080, "height": 1920, "rotation": 0, "opacity": 1 }, "image": { "assetId": "ASSET_HOOK", "kind": "background" } },
      { "id": "hook", "type": "text", "text": "5 desk swaps that fixed my back", "textRole": "hook-text", "textKind": "headline", "geometry": { "x": 90, "y": 320, "width": 900, "height": 300, "rotation": 0, "opacity": 1 }, "style": { "fontFamily": "Outfit", "fontSize": 88, "fontWeight": 800, "fontStyle": "normal", "fill": "#ffffff", "align": "center", "background": { "color": "#111111", "paddingX": 28, "paddingY": 22, "cornerRadius": 18 } } }
    ]
  },
  "altText": "Describe the actual hook image."
}
```

## B. Full-bleed body beat

Heading high, supporting sentence on a light card below it; both clear of the rail.

```json
{
  "scene": {
    "version": 1, "width": 1080, "height": 1920, "background": "#111111",
    "elements": [
      { "id": "bg", "type": "image", "geometry": { "x": 0, "y": 0, "width": 1080, "height": 1920, "rotation": 0, "opacity": 1 }, "image": { "assetId": "ASSET_BODY", "kind": "background" } },
      { "id": "heading", "type": "text", "text": "1. Raise the screen", "textRole": "content-text", "textKind": "headline", "geometry": { "x": 80, "y": 260, "width": 880, "height": 200, "rotation": 0, "opacity": 1 }, "style": { "fontFamily": "Outfit", "fontSize": 72, "fontWeight": 700, "fontStyle": "normal", "fill": "#ffffff", "align": "left", "background": { "color": "#111111", "paddingX": 24, "paddingY": 20, "cornerRadius": 16 } } },
      { "id": "body", "type": "text", "text": "Eye level stops the slow forward lean that loads your neck all day.", "textRole": "content-text", "textKind": "paragraph", "geometry": { "x": 80, "y": 500, "width": 860, "height": 300, "rotation": 0, "opacity": 1 }, "style": { "fontFamily": "Outfit", "fontSize": 50, "fontWeight": 500, "fontStyle": "normal", "fill": "#111111", "align": "left", "background": { "color": "#ffffff", "paddingX": 24, "paddingY": 20, "cornerRadius": 16 } } }
    ]
  },
  "altText": "Describe the actual body image."
}
```

## C. Two-image split (comparison, before/after)

Top and bottom halves, one label each, both inside the safe area.

```json
{
  "scene": {
    "version": 1, "width": 1080, "height": 1920, "background": "#111111",
    "elements": [
      { "id": "top", "type": "image", "geometry": { "x": 0, "y": 0, "width": 1080, "height": 960, "rotation": 0, "opacity": 1 }, "image": { "assetId": "ASSET_A", "kind": "background" } },
      { "id": "bottom", "type": "image", "geometry": { "x": 0, "y": 960, "width": 1080, "height": 960, "rotation": 0, "opacity": 1 }, "image": { "assetId": "ASSET_B", "kind": "background" } },
      { "id": "label-a", "type": "text", "text": "Linen", "textRole": "content-text", "textKind": "headline", "geometry": { "x": 80, "y": 780, "width": 440, "height": 110, "rotation": 0, "opacity": 1 }, "style": { "fontFamily": "Outfit", "fontSize": 64, "fontWeight": 700, "fontStyle": "normal", "fill": "#ffffff", "align": "left", "background": { "color": "#111111", "paddingX": 24, "paddingY": 16, "cornerRadius": 16 } } },
      { "id": "label-b", "type": "text", "text": "Cotton", "textRole": "content-text", "textKind": "headline", "geometry": { "x": 80, "y": 1000, "width": 440, "height": 110, "rotation": 0, "opacity": 1 }, "style": { "fontFamily": "Outfit", "fontSize": 64, "fontWeight": 700, "fontStyle": "normal", "fill": "#ffffff", "align": "left", "background": { "color": "#111111", "paddingX": 24, "paddingY": 16, "cornerRadius": 16 } } }
    ]
  },
  "altText": "Describe both images, top then bottom."
}
```

## D. Four-image grid (roundup, outfit set)

Cells of 540×960. A single centered heading sits across the seam, inside the safe area.

Image geometries: `{x:0,y:0}`, `{x:540,y:0}`, `{x:0,y:960}`, `{x:540,y:960}`, each `width 540, height 960`. Heading: `{ "x": 90, "y": 860, "width": 900, "height": 200 }` with the `hook` or `heading` style.

## E. Six-image grid (mood board, "my week in…")

Cells of 540×640 in two columns and three rows: `x` ∈ {0, 540}, `y` ∈ {0, 640, 1280}. Put one short heading at `{ "x": 90, "y": 560, "width": 900, "height": 180 }`. Keep text minimal; the grid is the message.

## F. Image-over-card (dense explanation)

Image across the top 1100 px, solid scene background below for longer copy.

Image: `{ "x": 0, "y": 0, "width": 1080, "height": 1100 }`. Scene `background`: a light color such as `#f5f1ea`. Heading at `{ "x": 80, "y": 1140, "width": 860, "height": 130 }` in dark text without a background box; body at `{ "x": 80, "y": 1280, "width": 860, "height": 210 }`. Stop text by `y` 1500.
