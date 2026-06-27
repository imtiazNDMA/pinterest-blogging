# Keyword Expansion Suggestions — how to find more keywords (PinClicks)

> **Generated:** 2026-06-27. **Updated:** 2026-06-27 after the 6 patio exports were ingested.
> **Dataset now:** 16 PinClicks exports, **4,413 unique interest terms / 7.84M SV pool.**
> **Purpose:** (1) inventory what you already have, (2) tell you exactly what to search/export next in
> PinClicks to grow coverage, (3) answer "can Claude connect to PinClicks directly."
> Companion docs: [`_pillar-subclusters-2026-06-26.md`](./_pillar-subclusters-2026-06-26.md) (balcony) ·
> [`_patio-subclusters-2026-06-27.md`](./_patio-subclusters-2026-06-27.md) (patio) ·
> [`_validation-volumes-2026-06-26.md`](./_validation-volumes-2026-06-26.md).

> [!done] 2026-06-27 progress — Patio arm ingested
> The P1 suggestion ("search `small patio ideas`") was actioned. 6 patio exports added **2,606 net-new terms
> (+1.17M SV)** and opened a full **Patio pillar** (6 sub-clusters) — see [`_patio-subclusters-2026-06-27.md`].
> `small patio ideas` real hub volume = **118,387** (vs the 5,096 we saw via balcony). Patio went 15 → 2,621 terms.

---

## 1. Can I connect to PinClicks myself?

**No — there's no API, and there's no way around the login.** [PinClicks](https://www.pinclicks.com/)
deliberately runs **no official Pinterest API account**; it reads publicly-viewable Pinterest data and
lets *you* export CSVs. There is no public API, no MCP connector, and the `app.pinclicks.com/keyword/...`
links inside your data sit behind your paid login, which I can't reach. (Sources:
[PinClicks](https://www.pinclicks.com/), [Keyword Explorer](https://www.pinclicks.com/keyword-explorer/),
[Simple Pin Media on the tool](https://www.simplepinmedia.com/pinterest-keyword-tool/).)

So the loop stays the same as your other data sources (Pinterest Trends / GA4 / Search Console):

> **You export the CSV → drop it in this folder → I process, dedupe, rank, and fold it into the cluster plan.**

That loop is fast and already proven — this whole analysis came out of it. What I *can* do is tell you
precisely **which searches to run**, so each export you spend brings back the most new, on-intent terms.

---

## 2. What you already have (inventory)

| Pillar | Hub term | Hub SV | Status |
|---|---|---|---|
| 1 — Decor & Styling | balcony ideas / balcony decor | 622,109 / 168,650 | deep, mapped |
| 2 — Furniture & Seating | balcony furniture | 18,490 | mapped (swing/seating sub-clusters) |
| 3 — Privacy & Shade | balcony privacy ideas | 20,364 | mapped (curtains/shade/screens) |
| 4 — Garden & Plants | balcony garden | 138,256 | mapped (the big engine) |
| 5 — Flooring | balcony tiles / flooring | 21,120 / 18,195 | thin |
| 6 — Lighting | balcony lights | 13,295 | mapped (fairy/string/ceiling) |

- **1,807 unique terms**, ~6.6M total search-volume pool, fully synthesized into the 6 pillars above.
- **Coverage is strong on `balcony` and basically complete** for that seed.

### Coverage by space (updated 2026-06-27)
Balcony and Patio are now both deep. The remaining adjacent spaces are still thin:

| Space | Terms exported | Note |
|---|---|---|
| balcony | 1,811 | saturated |
| patio | 2,621 | **now saturated** (added 2026-06-27) |
| garden | 807 | deep (spans both) |
| backyard | 76 | **thin — next priority** (frontier is loud here) |
| terrace | 21 | thin |
| porch | 21 | thin |
| deck | 38 | thin |
| **sunroom** | **1** | still ~nothing |

Balcony + Patio = the core niche, both mapped. The frontier (section 4) now points hard at **backyard**
(`small backyard ideas` 38x, `cozy backyard ideas` 32x) and patio long-tail refinements
(`back patio ideas`, `mini patio ideas`, `patio conversation set`, `outdoor patio seating`).

---

## 3. The method — snowball via "Related Interests"

PinClicks gives every interest a **Related Interests** list (~6–10 neighbors). The fastest way to grow
without guessing:

1. Export an interest's page → it carries its neighbors.
2. The neighbors you **haven't exported yet** = your "frontier."
3. Search/export the highest-value frontier terms → they bring *their* neighbors → repeat.

I computed your current frontier automatically: **1,259 referenced interests are not yet in your exports.**
After filtering off-intent noise, the priority seeds are in section 4. The number next to each seed is how
many of your existing terms point to it (a free demand proxy — higher = more central to the interest graph).

---

## 4. Search/export these next in PinClicks (prioritized)

Run these as **new keyword searches** in PinClicks, export each result CSV into this folder, and tell me.
Ordered by expected payoff. Each seed will snowball its own neighbors, so ~12 searches will likely double
your mapped niche.

### ✅ DONE 2026-06-27 — Patio arm (was Priority 1)
`small patio ideas`, `patio design`, `patio garden`, `patio gardening`, `patio privacy`, `patio furniture`
all exported and ingested → Patio pillar mapped. See [`_patio-subclusters-2026-06-27.md`].

### 🟢 Priority 1 (new) — the Backyard arm (frontier is loud; on-brand small-space styling)
```
small backyard ideas         (38x)   ← do this first now; most-referenced term you don't have
cozy backyard ideas          (32x)
small backyard privacy ideas (16x)
gazebo ideas backyard        (17x)
small back garden ideas      (12x)
```
> Intent check before committing posts: keep the **small / cozy / privacy** long-tail (renter-relevant);
> skip big-build landscaping ("backyard makeover" with pools/decks/contractor scope).

### 🟢 Priority 2 — Patio long-tail refinements (deepen the new pillar)
```
back patio ideas             (33x)
mini patio ideas / tiny patio ideas   (30x / 13x)
outdoor patio seating ideas  (27x)
patio conversation set ideas (30x)   ← buyer/money (furniture sets)
patio set up ideas           (25x)
covered patio ideas          (11x)
```

### 🟢 Priority 3 — DIY / Pallet seating (coherent buyer + DIY sub-cluster, spans balcony+patio)
```
pallet furniture outdoor      (sums ~20x across pallet variants)
outdoor conversation sets     (20x)   ← buyer/money
outdoor couch ideas           (12x)
outside furniture ideas       (16x)
diy balcony furniture
```

### 🟡 Priority 4 — Seasonal (plan 6–8 weeks ahead of each season; patio/balcony lighting + seasonal came back empty in the topic exports — pull dedicated seeds)
```
halloween front porch decorating ideas   (4x)   ← US seasonal, high pin velocity
apartment porch christmas decor           (2x)
christmas balcony decor / outdoor christmas lights ideas
fall balcony / autumn balcony decor
```
> Note: filter out **Diwali** lighting/decor seeds — high volume but wrong market (India construction/festival),
> same off-intent bucket as railing/grill design.

### 🟡 Priority 5 — fill thin pillars
```
Flooring:  outdoor floor tile design · outdoor deck tiles · deck flower boxes · outside flooring ideas
Shade:     sunshade ideas outdoor spaces · outdoor roller blinds · canopy ideas outdoor · pergola ideas
Garden:    small space vegetable garden · porch herb garden · vertical garden wall outdoors · plant boxes outdoor
```

---

## 5. Don't waste exports on these (off-intent — confirmed)

These show high volume but pull the wrong audience (architecture/construction, non-US market, or games),
matching the exclusions already noted in your validation doc:

- **Construction / railing:** balcony/terrace **railing design**, **grill design**, iron/MS/steel railing,
  glass railing, elevation designs, false/fall **ceiling design**, parapet, handrail.
- **Wrong market (India build/festival):** open terrace ideas india, indian home garden design, Diwali lighting.
- **Interior remodel:** wardrobe design, tv unit, upvc doors, sliding window design.
- **Games / not-real-spaces:** minecraft, bloxburg, **toca boca** anything.
- **People, not spaces:** balcony/terrace **photoshoot ideas**, picture poses, "best poses for pictures."

When a new export arrives, I auto-drop anything matching these patterns before ranking.

---

## 6. What to hand me after each export

Just drop the CSV(s) in `keyword Research/` and say "process these." I will:
1. Dedupe by interest ID against the existing 1,807.
2. Filter off-intent (section 5 patterns).
3. Rank new terms by real Search Volume and tag intent (decor / buyer / DIY / seasonal).
4. Slot them into the right pillar in `_pillar-subclusters-*.md` and surface any new post-worthy clusters.
5. Recompute the frontier so the *next* batch of seeds is ready.

> **Fastest single action right now:** in PinClicks, search **`small backyard ideas`**, export, and drop it here.
> With patio done, backyard is the loudest remaining frontier (38 of your terms point to it) and rounds out
> the small-space outdoor-styling niche (balcony · patio · backyard).
