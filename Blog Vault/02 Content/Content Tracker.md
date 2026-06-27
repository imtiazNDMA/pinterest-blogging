---
type: content-tracker
updated: 2026-06-26
---

# 📝 Content Tracker

← [[Home]] · [[Content Calendar]] · [[Content Backlog & Ideas]] · [[Content Workflow]]

Every post and its status. Mirrors the production studio's master CSV; this is the human-friendly view.
**Status flow:** Idea → Draft → Ready → Published → Updated.

## Live + ready posts (Pillar 1 — Decor & Styling)
| Post | Slug | Primary keyword (Pinterest target) | Status | Pins | Owner inputs left |
|---|---|---|---|---|---|
| Small Balcony Ideas (PILLAR) | `small-balcony-patio-ideas` | balcony ideas / small balcony design | Ready | PB-005 | photos×5, affiliate links, [PERSONAL TIP] |
| Cozy Small Balcony Ideas | `cozy-small-balcony-ideas` | cozy balcony / cozy balcony aesthetic | Ready | PB-001 | photos×4, affiliate links, [PERSONAL TIP] |
| Small Balcony Ideas on a Budget | `small-balcony-ideas-on-a-budget` | small balcony ideas on a budget | Ready | PB-002 | photos×4, affiliate links, [PERSONAL TIP] |
| Renter-Friendly Balcony Ideas | `renter-friendly-balcony-ideas` | small balcony decor (Google-lean) | Ready | PB-003 | photos×4, affiliate links, [PERSONAL TIP] |
| Small Balcony Makeover B&A | `small-balcony-makeover-before-and-after` | balcony makeover | Ready | PB-004 | photos×5, affiliate links, [PERSONAL TIP] |
| Balcony Privacy Ideas | `balcony-privacy-ideas-for-apartments` | balcony privacy ideas (20k) | Ready | PB-006 | photos×5, affiliate links, [PERSONAL TIP] |
| Best Self-Watering Planters | `best-self-watering-planters-balcony` | self-watering planters balcony | Ready | — | photos×2, affiliate links |

**6 posts READY** (5 in the decor cluster + 1 planters). Privacy closes the pillar + renter stub links.

## Next to write (validated priority)
| Post | Target keyword | SV | Priority |
|---|---|---|---|
| Apartment Balcony Decorating | apartment balcony decorating | 69,133 | **P1 — next** (new) |
| Modern Balcony Ideas | modern balcony ideas | 56,629 | P1 (new) |
| Boho Balcony Ideas | boho balcony | 16,079 | P1 |
| Best Balcony Furniture | balcony furniture | 18,490 | P1 (Pillar 2 / money) |
| Balcony Garden Ideas | balcony garden ideas | 77,684 | P1 (Pillar 4) |
| Cozy Winter Balcony | winter balcony | 4,013 | P2 seasonal |

Full backlog + demoted ideas → [[Content Backlog & Ideas]].

## Publishing checklist (per post, before hitting Publish)
- [ ] Owner inputs filled (real photos, [PERSONAL TIP])
- [ ] `Bloom & Lantern` / `https://bloomandlantern.com` / `{{AMAZON_TAG}}` tokens replaced
- [ ] Affiliate links real + FTC disclosure above first link
- [ ] Category assigned ([[WordPress Categories & Tags]]); 3+ internal links
- [ ] Meta title + description set; featured image set
- [ ] Pin batch designed + scheduled ([[Pin Tracker]])

> [!note] Optional Dataview
> ```dataview
> TABLE status, pillar, pins FROM "02 Content" WHERE type = "post" SORT status
> ```
