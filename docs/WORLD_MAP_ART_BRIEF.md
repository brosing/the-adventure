# World Map — Illustration Brief

Geography and place names below are pulled directly from the shipped Game I chapters (not invented) plus Lumenvale for Game II.

---

## Style Direction

- **Medium**: hand-painted fantasy map illustration — gouache or watercolor texture, visible brushstrokes, aged parchment or dark canvas base. Think classic storybook end-paper maps (The Hobbit, Winnie-the-Pooh's Hundred Acre Wood, Narnia) crossed with a quiet, modern editorial illustration style.
- **Palette**: dark, late-night background (deep blue-black, not pure black) with warm amber/gold ink and highlights — matches the project's shared visual language across all three surfaces (dark oklch themes, warm amber accents). Cool muted teal for water. Muted sage/forest green for trees. No saturated or neon colors.
- **Mood**: cozy, quiet, a little melancholic, magical-realist — not epic or dramatic. Nothing looks conquered or militarized (no flags, no borders, no "kingdoms"). This is a map of a fairy tale, not a fantasy war epic.
- **Line work**: fine ink linework for roads and labels-frames, loose and slightly imperfect (hand-drawn, not vector-precise).
- **Typography** (if the tool renders text): warm serif, editorial, small caps or italic for place names — but expect AI tools to render text poorly. Recommended: generate the illustration with NO text baked in, then overlay labels afterward using `docs/WORLD_MAP.svg`'s text layer as a positioning guide, or add labels manually in a design tool.

---

## Composition (north at top)

A single continuous illustrated landscape, not a grid or split panels. Roughly this vertical arrangement, north to south:

1. **Far north**: a small hidden garden glowing faintly, ringed by frost that stops abruptly at its border — "The First Quiet."
2. Just below: a single ancient stone well standing alone in open land.
3. A two-peaked mountain range with a valley of tiny floating lights visible just beyond one pass.
4. To the northeast: a vast, perfectly still, mirror-flat sea — no waves, no ripples, wide and lonely.
5. A small stone-cottage windmill village tucked in a narrow valley between two mountains, with a thin river and a lone cedar tree.
6. Descending south: rolling hills, then a dense dark forest with one silver-barked, mirror-leaved tree glowing faintly at its heart, and one small gray withering tree at its edge.
7. A cozy stone cottage beside a perfectly still pond, moss-roofed, one warm lantern lit, near a narrow stone bridge with a signpost.
8. More rolling hills, and one ancient solitary willow tree standing apart from any road.
9. **Center**: the town of Bellwood — a cluster of close, warm-lit rooftops around a town square where six roads meet, a market, an old leaning clock tower, and one three-story shop with a sign. A slim river runs along the town's southern edge. One small house sits at the town's edge, closest to open grass.
10. South of Bellwood, a lone stone structure in the hills — windowless, one wooden door.
11. **Far south**: Lumenvale — a bright, prosperous city of white stone and golden rooftops, flower-filled balconies, canals with elegant bridges, and a large central fountain, its water reduced to a trickle.

Connect the settlements with thin, hand-drawn dotted or dashed paths (footpaths, not roads) — this is a walking world, never a driving one.

---

## Full Location List (for prompt detail / label overlay)

**Bellwood** (Game I & III)
- Market of Loud Things — town market, where six roads meet
- Ticktock & Company — three-story shop in the square
- The old leaning clock tower
- Asa's home, at the edge of town
- The bakery, the schoolyard, the last lamppost
- The bridge over the river
- The willow tree — beyond the places marked on town maps

**North of Bellwood**
- Bellwood's Northern Hills
- The stone bridge & signpost ("Those who are looking for noise are already lost")
- The Keeper's Cottage, beside a still pond
- The Listening Forest — the Silver Tree (center), the Gray Tree (edge, withering)
- The windmill village (Quiet Valley) — stone cottages, small river, a cedar tree
- A Silence Well, standing alone
- Mountain of Forgotten Dreams, with the Valley of Lights just beyond
- Sea of Still Waters (the Quiet Whale sleeps beneath) — to the northeast
- The First Quiet — hidden garden, frost stops at its border, birthplace of all silence

**South of Bellwood**
- Room of Unspoken Words — windowless stone structure, single door inscribed "WHAT IS UNSAID REMAINS"
- Lumenvale (Game II) — white stone, golden rooftops, canals, a central fountain gone quiet, a small inn

---

## Ready-to-Use Prompt (Midjourney-style)

```
a hand-painted fantasy storybook map, gouache and watercolor texture on dark
midnight-blue parchment, warm amber ink linework, cozy melancholic fairy-tale
atmosphere, no text, illustrated top-down landscape flowing north to south:
a small glowing hidden garden ringed by frost at the very top, one lone ancient
stone well, twin misty mountains with tiny floating lights in a hidden valley,
a vast perfectly still mirror-flat sea to the northeast, a tiny windmill village
in a narrow valley with a thin river, rolling hills, a dark whispering forest
with one silver glowing tree at its heart, a small cottage beside a still pond
with one lit window, more hills, one solitary willow tree, a warm-lit small
town at the center with six roads meeting at a square and a leaning clock
tower, a slim river along its edge, one lone windowless stone structure in
southern hills, and a bright prosperous city of white stone and golden
rooftops with canals and a quiet fountain at the very bottom — thin dashed
footpaths connecting every place, muted teal water, muted sage forests, no
modern elements, no photorealism, storybook illustration style like The Hobbit
or Winnie-the-Pooh endpaper maps --ar 4:3 --style raw
```

**Negative prompt** (if supported): text, letters, words, labels, photorealistic, 3D render, neon colors, harsh contrast, modern city, cars, weapons, flags, war, crowns, castles with battlements
