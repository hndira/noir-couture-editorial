---
name: noir-couture-editorial
description: >-
  Create images or image prompts for dark couture posters (暗调高定海报),
  neo-Chinese fashion lookbooks (新中式画册), and bilingual luxury magazine
  covers (时尚杂志封面). Pairs studio lighting and garment-matched lettering
  with full-length poster or layered cover compositions.
---

# Noir Couture Editorial

Start with the garment, the intended format, and the words the reader must see. Preserve the user's subject, fabric, color, title, language, and requested dimensions. Use the following defaults to fill gaps.

## Choose the composition

| Mode | Use when | Compose around |
| --- | --- | --- |
| `poster` | A full silhouette, runway look, or lookbook sheet | Frame head to shoes against matte obsidian concrete. Leave side space for the title and ground the hem and shoes with a soft contact shadow. |
| `cover` | A magazine issue or portrait-led cover | Use a seated or three-quarter portrait against warm charcoal-taupe. Place a wide, condensed masthead behind the crown or hairpin. Keep enough of each letter visible to recognize the name. |

Start at 3:4 portrait. Shape the fabric with a soft directional key and separate dark edges with a fine rim light. Keep skin and weave texture visible. Use warm ivory type and one or two crimson graphic motifs (`#B81D24`, up to about 5% of the canvas). A requested crimson or ink-green garment keeps its own color. For a series, carry the framing, light direction and margins across looks. The [style guide](./references/style-dna.md) gives the grids, palette and lighting positions.

## Set the lettering and assemble the prompt

1. Quote each requested line exactly, including case and punctuation. If copy is open, choose a garment-specific Chinese title of 2–4 characters and a short English counterpart. Aim for about 30 Chinese characters across all optional and required copy together. Drop optional lines first. For a text-free request, use the composition with all lettering, seals and issue metadata omitted.
2. Choose one visual feature of the garment to echo in the title strokes. For example, give sheer organza thin, tapered strokes and an airy italic caption. Give angular tailoring a condensed, split-stroke title. Use the [garment-to-type matrix](./references/style-dna.md#garment-to-typography-design-matrix) for other pairings. For an unspecified masthead, invent an editorial name and avoid copying a magazine logo.
3. Choose the closest [prompt template](./references/prompt-templates.md). Fill the fields for the chosen blocks, remove unused blocks, then check for leftover braces and unrequested text. The [six showcase prompts](./examples/showcase-prompts.md) illustrate specific garments and copy choices.

## Deliver and check the result

For a prompt request, return the completed prompt. For an image request, use the host's image generator when available. If the host lacks image generation, supply the ready-to-use prompt and identify it as such.

Inspect each generated image at a readable size. Check the requested framing, the garment's color and texture, every quoted line, and whether the red accents compete with the outfit. On covers, check both the masthead overlap and its legibility. If a defect is visible, make one targeted correction and inspect the result again. For persistent lettering errors, identify the affected line and provide its exact wording and placement for typesetting. Preserve supplied text throughout.
