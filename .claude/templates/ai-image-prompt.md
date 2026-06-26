# Template: AI Image Prompts (plug-and-play)

Copy a block, fill the `[SLOTS]`, paste into your AI image tool. Obeys
`guardrails/ai-image-generation.md`; style from `guidelines/pin-visual-style.md`; procedure in
`playbooks/pin-image-generation.md`. Pins are **always 2:3 / 1000×1500**.

---

## Two paths (pick one per pin)
- **Path A — AI renders the text.** Fast. Only for **very short ALL-CAPS hero words**; AI garbles longer text.
  Proofread letter-by-letter. Use the `OVERLAY (Path A)` line.
- **Path B — recommended.** Generate a **clean plate with negative space, no text**, then add overlay text in
  **Canva** with brand fonts (crisp, editable, on-brand). Use the `CLEAN PLATE (Path B)` line and skip the text line.

## Tool notes
| Tool | Aspect ratio | Text | Tip |
|---|---|---|---|
| ChatGPT / DALL·E | say "vertical 2:3, 1024×1536" | weak on long text → Path B | good scenes; export, resize to 1000×1500 |
| Google Gemini / Imagen | "2:3 vertical" | better text, still proof | strong photoreal |
| Midjourney | `--ar 2:3` | weak → Path B | best aesthetics; reuse `--sref [id]` across a batch for cohesion |

## Universal style suffix (paste at the end of every prompt)
```
Style: warm, soft natural golden-hour light, editorial home-decor photography, authentic and photographic,
lived-in, cozy. Palette: warm cream, honey wood, terracotta, sage green, soft charcoal, amber light, dusk blue.
Composition: rule of thirds, clear focal point, real depth, intentional negative space for text. Small-balcony
scale (narrow apartment ledge, real railing). 2:3 vertical, 1000x1500, high resolution.
```

## Universal negative prompt (always include)
```
Negative: warped or impossible railings/architecture, melted or doubled string lights, floating furniture,
extra fingers, distorted faces, gibberish or misspelled text, CGI plastic sheen, oversaturation, HDR halos,
fisheye, watermark, brand logos, signatures, on-image prices, dead or wrong-season plants, clutter.
```
(Midjourney: use `--no warped railings, extra fingers, text, watermark, logo`.)

---

## Archetype prompts

### 1. Aesthetic Hero (full-bleed + lower-third text band)
```
A [BALCONY SCENE: e.g. cozy small apartment balcony corner at dusk] with [KEY ELEMENTS: outdoor rug over
concrete, one cushioned chair with a throw, warm string lights overhead, layered potted plants on the rail].
Low three-quarter angle. Keep the lower third simpler/darker for a text band.
OVERLAY (Path A): bottom cream band, charcoal serif ALL-CAPS text "[≤8-WORD HOOK]".
CLEAN PLATE (Path B): leave the lower third as calm negative space, no text.
+ [universal style suffix] + [negative]
```

### 2. Number / List Grid (2×3 or 3×3 + big number)
```
A clean [2x3] grid of tidy, consistent home-decor vignettes, each a distinct small-balcony idea
[LIST: rug, solar lights, painted pots, foldable chair, fabric privacy, floor cushion]. Even spacing,
same photographic style and scale in every cell, bright soft daylight.
OVERLAY (Path A): top header bar with an oversized number "[N]" and "[SHORT TITLE]".
CLEAN PLATE (Path B): leave a clean header strip at top, no text.
+ [universal style suffix] + [negative: ...gibberish labels...]
```

### 3. Before / After Split (vertical 50/50)
```
A vertical before-and-after split of the SAME small balcony from the SAME camera angle. Top half "before":
[BARE STATE: empty grey concrete, blank railing, flat daylight]. Bottom half "after": the identical balcony
styled with [AFTER ELEMENTS: rug, anchor chair + cushion, warm string lights, plants], warm golden glow.
Realistic, believable transformation — not exaggerated.
OVERLAY (Path A): thin "BEFORE" tag top corner, "AFTER" tag bottom corner, seam banner "[SHORT HOOK]".
CLEAN PLATE (Path B): leave a clean middle seam for a banner, no text.
+ [universal style suffix] + [negative]
```

### 4. Comparison Split (left/right, e.g. spend vs save)
```
A vertical pin split into two labeled columns. Left "[LABEL A: SPEND]": [ITEMS A: good outdoor rug, warm
string lights]. Right "[LABEL B: SAVE]": [ITEMS B: foldable chair, painted pots, thrifted lantern]. Clean
divider down the center, warm and bright, infographic-meets-photo but cohesive.
OVERLAY (Path A): header "[HOOK]", small "[LABEL A]" / "[LABEL B]" over each column.
CLEAN PLATE (Path B): leave header strip + space over each column clean, no text.
+ [universal style suffix] + [negative]
```

### 5. Category Quadrant (2×2 + center badge)
```
A 2x2 grid of four cohesive small-balcony vignettes: top-left [SEATING], top-right [LIGHTING],
bottom-left [PRIVACY], bottom-right [PLANTS]. Same warm palette and lighting across all four; slim gutters.
OVERLAY (Path A): clean corner label per quadrant + center badge "[BRAND/HOOK]".
CLEAN PLATE (Path B): leave a small center circle and corner spaces clean, no text.
+ [universal style suffix] + [negative]
```

### 6. Formula / Diagram Stack (numbered steps)
```
A vertical diagram-style pin of [N] stacked steps, each a soft photo strip of that element
[STEPS: declutter, floor, anchor seat, greenery, warm light, personal layer], numbered 1..[N] down the side.
Cozy warm tint, clean and clear, decor-not-tech-chart.
OVERLAY (Path A): top title bar "[FORMULA TITLE]"; crisp step numbers.
CLEAN PLATE (Path B): leave the title bar and number spots clean, no text.
+ [universal style suffix] + [negative]
```

### 7. Text-Forward Tease (photo strip + headline panel)
```
Upper two-thirds: a soft, gently blurred photographic strip of [STYLED BALCONY CORNER]. Lower third: a clean
[cream] panel for a large headline. Optional small flat "[BADGE: NO HOLES]" stamp in a corner.
OVERLAY (Path A): bold charcoal headline on the cream panel "[CURIOSITY HOOK]".
CLEAN PLATE (Path B): keep the cream panel empty, no text.
+ [universal style suffix] + [negative]
```

### 8. Single Product / Flat-lay
```
A single [PRODUCT: clamp-on railing planter / solar string lights / outdoor rug] styled on a small balcony,
or a tidy flat-lay of it, warm daylight, clean uncluttered background, one clear hero object. No brand logos.
OVERLAY (Path A): small corner label "[BEST FOR ...]".
CLEAN PLATE (Path B): leave one corner calm for a label, no text.
+ [universal style suffix] + [negative]
```

---

## Fill-from-the-brief
Every pin block in `Content/pins/<slug>-pins.md` already gives you the scene, overlay text, palette cue, and
filename. Map: **design brief → archetype → fill slots → add suffix + negative → generate**. Then run the
`playbooks/pin-image-generation.md` QA before publishing. Reuse one Midjourney `--sref` (or one seed/style)
across a batch for cohesion.
