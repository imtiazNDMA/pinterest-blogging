# Guideline: Topic Cluster & Keyword Schema

How keyword research is organized so content compounds (pillar + supporting posts, interlinked).

## The cluster model
- **Pillar post:** broad, high-level guide for the cluster's head term (e.g., "Balcony Vegetable Gardening").
- **Supporting posts:** long-tail, specific intents that each link up to the pillar and sideways to siblings.
- A cluster = 1 pillar + 5–12 supporting posts. Clusters map to the 4 content pillars (see `.claude/memory.md`).

## Keyword record fields (logged in `keyword Research/<cluster>.md` or `.csv`)
| Field | Meaning |
|---|---|
| `keyword` | the exact long-tail phrase |
| `intent` | informational \| buyer \| navigational |
| `cluster` | parent cluster slug |
| `role` | pillar \| supporting |
| `est_volume` | rough monthly searches — **label `(est — needs validation)`** unless from a real tool |
| `difficulty` | low/med/high estimate (SERP + competition reasoning) |
| `pinterest_signal` | autocomplete/Trends evidence of Pinterest demand |
| `monetizable` | yes/no + how (Amazon? garden program? ad-only?) |
| `priority` | P1/P2/P3 (demand × ease × money) |
| `suggested_title` | working post title |
| `status` | idea → brief → drafting → published |

## How a seed becomes a cluster (keyword-researcher does this)
1. Take a pillar/seed (e.g., "balcony vegetables").
2. Expand via Pinterest autocomplete, Google autocomplete, "People Also Ask," related searches.
3. Tag intent; group into pillar vs supporting.
4. Estimate difficulty/volume (clearly labeled as estimates) + Pinterest demand signal.
5. Score priority = demand × rankability × monetization fit.
6. Output a **cluster map** (`templates/cluster-map.md`) + a **content brief** per P1/P2 post.

## Prioritization heuristic
- **P1:** clear Pinterest demand + low difficulty + monetizable or strong ad-intent. Write these first.
- **P2:** good demand, medium difficulty, or informational/ad-only.
- **P3:** nice-to-have, higher difficulty, or thin demand.

## Validation gate
Numbers from autocomplete/reasoning are **estimates**. Before betting heavily on a cluster, the user
pastes Keyword Planner / Pinterest Trends exports; keyword-researcher then updates `est_volume` and
removes the `(est)` label. Never present estimates as confirmed data.
