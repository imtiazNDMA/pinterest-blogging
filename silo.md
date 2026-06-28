# Silo Map — Bloom & Lantern (hub-and-spoke "soft silo")

> **Purpose:** upload all 57 written articles into clean topical silos so Google reads the site as an organized authority, not a pile of posts. Use this as the publish + internal-linking blueprint.
> **Soft silo = structure by internal links + categories, not by URL folders.** Keep your flat permalink (`/%postname%/`). The siloing comes from (a) which **category** a post sits in and (b) **which posts link to which** — most links stay *inside* the silo; cross-silo links are few and deliberate.

---

## The 3 rules that make a soft silo work

1. **Publish the HUB first.** Every spoke links up to its hub, so the hub must exist or those links 404. Hubs are also your money/head-term landing pages.
2. **Link tightly inside the silo, sparingly across silos.**
   - **Hub → all its spokes** (a "Read next / In this guide" list in the hub body).
   - **Each spoke → its hub** (one clear up-link, ideally early) **+ 2-4 sibling spokes** in the same silo.
   - **Across silos:** link only where genuinely useful (the short "Cross-silo bridges" list below). Every cross-silo link slightly leaks the silo's focus, so be intentional.
3. **One category per post** = its silo's category. Don't tick multiple categories; that blurs the silo.

> Good news: the drafts are already wired this way — each post's `internal_links` frontmatter mostly points to its hub + siblings. This doc just makes the structure explicit and gives the upload order.

---

## Two top categories (create these first)
- **Balcony Ideas** — 40 posts (6 silos)
- **Patio Ideas** — 17 posts (4 silos)

*(Optional, stronger structure: add the 10 silos below as **sub-categories** under those two parents, e.g. Balcony Ideas → Furniture. Not required for a soft silo, but it gives cleaner breadcrumbs and archive pages. Keep the flat URL either way.)*

---

# CATEGORY: BALCONY IDEAS

## Silo B1 — Small Balcony Ideas (Decor & Styling)
**HUB:** `small-balcony-patio-ideas` *(publish 1st in this silo)*
| Spoke | slug |
|---|---|
| Cozy small balcony | `cozy-small-balcony-ideas` |
| Budget balcony | `small-balcony-ideas-on-a-budget` |
| Renter-friendly balcony | `renter-friendly-balcony-ideas` |
| Balcony makeover (before/after) | `small-balcony-makeover-before-and-after` |
| Modern balcony | `modern-balcony-ideas` |
| Balcony aesthetic | `balcony-aesthetic` |
| Boho balcony | `boho-balcony-ideas` |
| Apartment balcony decorating | `apartment-balcony-decorating` |

## Silo B2 — Balcony Furniture & Seating
**HUB:** `balcony-furniture-ideas`
| Spoke | slug |
|---|---|
| $ Swing / hanging chairs | `balcony-swing-chairs` |
| $ Best balcony chairs | `best-balcony-chairs` |
| Balcony seating ideas | `balcony-seating-ideas` |
| $ Balcony sofa | `balcony-sofa-ideas` |
| $ Balcony bench | `balcony-bench-ideas` |
| $ Table & chairs (bistro) | `balcony-table-and-chairs` |

## Silo B3 — Balcony Privacy & Shade
**HUB:** `balcony-privacy-ideas-for-apartments`
| Spoke | slug |
|---|---|
| $ Balcony curtains | `balcony-curtain-ideas` |
| $ Balcony shade | `balcony-shade-ideas` |
| Privacy screens (buy + DIY) | `balcony-privacy-screens` |
| $ Balcony blinds | `balcony-blinds` |
| Balcony trellis | `balcony-trellis-ideas` |
| How-to: cover a railing for privacy | `how-to-cover-balcony-railing-for-privacy` |

## Silo B4 — Balcony Garden & Plants ⚠ (YMYL)
**HUB:** `balcony-garden-ideas`
| Spoke | slug |
|---|---|
| Best balcony plants | `best-balcony-plants` |
| Small balcony garden | `small-balcony-garden` |
| Apartment balcony garden | `apartment-balcony-garden` |
| Balcony flowers | `balcony-flowers` |
| Balcony hanging plants | `balcony-hanging-plants` |
| Balcony vegetable garden | `balcony-vegetable-garden` |
| $ Balcony railing planters | `balcony-railing-planters` |
| Vertical balcony garden | `vertical-balcony-garden` |
| $ Best self-watering planters | `best-self-watering-planters-balcony` |

## Silo B5 — Balcony Flooring
**HUB:** `balcony-flooring-ideas`
| Spoke | slug |
|---|---|
| $ Balcony deck tiles | `balcony-deck-tiles` |
| $ Outdoor rugs for balconies | `outdoor-rugs-for-balconies` |

## Silo B6 — Balcony Lighting
**HUB:** `balcony-lighting-ideas`
| Spoke | slug |
|---|---|
| $ Balcony fairy / string lights | `balcony-fairy-lights` |
| $ Balcony ceiling / hanging lights | `balcony-ceiling-lights` |
| Balcony christmas lights (seasonal) | `balcony-christmas-lights` |

---

# CATEGORY: PATIO IDEAS

## Silo P1 — Small Patio Ideas (Decor, Living & Care)
**HUB:** `small-patio-ideas`
| Spoke | slug |
|---|---|
| Small patio decorating | `small-patio-decorating-ideas` |
| Apartment / townhouse patio | `apartment-patio-ideas` |
| How-to: get rid of flies on a patio | `how-to-get-rid-of-flies-on-patio` |
| How-to: clean a concrete patio | `how-to-clean-concrete-patio` |
| How-to: paint a concrete patio | `how-to-paint-concrete-patio` |
| How-to: hang patio lights | `how-to-hang-patio-lights` |

## Silo P2 — Patio Garden & Plants ⚠ (YMYL)
**HUB:** `patio-garden-ideas`
| Spoke | slug |
|---|---|
| Small patio garden | `small-patio-garden` |
| Cottage / English garden patio | `cottage-garden-patio` |
| Apartment patio garden | `apartment-patio-garden` |

## Silo P3 — Patio Furniture & Seating
**HUB:** `patio-furniture-ideas`
| Spoke | slug |
|---|---|
| DIY patio furniture | `diy-patio-furniture` |
| $ Best wicker / wrought-iron furniture | `best-wicker-patio-furniture` |
| Patio furniture layout (how-to) | `patio-furniture-layout-ideas` |
| How-to: clean patio furniture | `how-to-clean-patio-furniture` |

## Silo P4 — Patio Privacy & Shade
**HUB:** `patio-privacy-ideas` *(hub only so far — spokes not yet written)*

---

## Cross-silo bridges (the ONLY links that should cross silos)
Keep these few; they are genuinely relevant and help the reader without dissolving the silos:
- `balcony-privacy-ideas-for-apartments` ⇄ `patio-privacy-ideas` (same problem, two spaces)
- `balcony-furniture-ideas` ⇄ `patio-furniture-ideas`
- `balcony-garden-ideas` ⇄ `patio-garden-ideas`
- `apartment-balcony-decorating` ⇄ `apartment-patio-ideas` (the apartment/renter reader)
- `how-to-clean-patio-furniture` → `best-wicker-patio-furniture` (care supports the buyer post)
- `how-to-hang-patio-lights` → `balcony-lighting-ideas` (one nod between the lighting topics)
- The homepage links to **all 10 hubs** (it sits above the silos, so it is allowed to link everywhere).

> Everything else: link **within** the silo only. If you feel the urge to link a balcony decor post to a patio furniture post, resist it unless the sentence truly needs it.

---

## Visual tree
```
Bloom & Lantern (homepage -> links to all 10 hubs)
│
├─ CATEGORY: Balcony Ideas
│   ├─ B1 Small Balcony Ideas (hub) ── 8 spokes (cozy, budget, renter, makeover, modern, aesthetic, boho, apartment)
│   ├─ B2 Balcony Furniture (hub) ──── 6 spokes (swing, chairs, seating, sofa, bench, table)
│   ├─ B3 Balcony Privacy (hub) ────── 6 spokes (curtains, shade, screens, blinds, trellis, cover-railing)
│   ├─ B4 Balcony Garden (hub) ─────── 9 spokes (plants, small-garden, apt-garden, flowers, hanging, veg, railing-planters, vertical, self-watering)
│   ├─ B5 Balcony Flooring (hub) ───── 2 spokes (deck-tiles, rugs)
│   └─ B6 Balcony Lighting (hub) ───── 3 spokes (fairy, ceiling, christmas)
│
└─ CATEGORY: Patio Ideas
    ├─ P1 Small Patio Ideas (hub) ──── 6 spokes (decorating, apartment, flies, clean-concrete, paint-concrete, hang-lights)
    ├─ P2 Patio Garden (hub) ───────── 3 spokes (small-garden, cottage, apartment)
    ├─ P3 Patio Furniture (hub) ────── 4 spokes (diy, wicker, layout, clean-furniture)
    └─ P4 Patio Privacy (hub) ──────── (spokes TBD)
```

---

## Upload order (per silo: hub first, then spokes)
1. **All 10 hubs first** (across both categories) so every up-link resolves: `small-balcony-patio-ideas`, `balcony-furniture-ideas`, `balcony-privacy-ideas-for-apartments`, `balcony-garden-ideas`, `balcony-flooring-ideas`, `balcony-lighting-ideas`, `small-patio-ideas`, `patio-garden-ideas`, `patio-furniture-ideas`, `patio-privacy-ideas`.
2. Then publish each silo's spokes **as a group** (so the cluster lights up together and the hub's "read next" links all resolve).
3. In each hub, add/confirm a **"Guides in this series"** block linking to every spoke. In each spoke, confirm the **up-link to the hub** sits in the intro and **2-4 sibling links** appear in the body.
4. Assign the **one** correct category as you publish. Set the featured image.

*(This pairs with `Growth Strategy/launch-plan.md`, which sequences hubs → money posts → the rest by priority. Use launch-plan.md for "what to publish first for traffic/revenue"; use this silo.md for "how the links + categories are wired.")*

## Counts
- Balcony Ideas: 40 (B1 9 · B2 7 · B3 7 · B4 10 · B5 3 · B6 4)
- Patio Ideas: 17 (P1 7 · P2 4 · P3 5 · P4 1)
- **Total written: 57.**
