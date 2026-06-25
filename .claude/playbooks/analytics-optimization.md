# Playbook: Analytics & Optimization Loop (Milestone 6 — "Stable Side Income")

Used by **analytics-optimizer** / `/weekly-review`. Improve what works; cut what doesn't. Decisions from
data, never vanity metrics alone.

## Data sources (user pastes; agent never invents numbers)
- **GA4:** sessions, pageviews, avg time on page, top posts.
- **Search Console:** impressions, clicks, CTR, queries the site ranks for.
- **Pinterest analytics:** impressions, saves, outbound clicks per pin/board.
- **Amazon/affiliate reports:** clicks, ordered/shipped items, revenue, commission, EPC.
- **Ad dashboard:** sessions, RPM, revenue.
All flow into `pinterest_blog_master_tracker.csv` (system of record).

## Weekly operating cadence (~20 hrs split per memory.md)
- Publish 1–3 new posts; create 10–20 new pins; refresh 1 older post.
- Review Pinterest analytics + Search Console; add internal links between related posts.
- Improve titles/descriptions for posts with impressions but low clicks.

## The optimization questions
1. Which posts/pins get **outbound clicks**? → expand into more cluster posts + more fresh pin angles.
2. Which pin titles get **saves**? → reuse that hook style.
3. Which designs get **impressions but no clicks**? → redesign or retire the angle.
4. Which **Search Console queries** does the site rank for but didn't target? → new post ideas.
5. Which boards/clusters gain traction? → double down.
6. Where's the money (EPC, conversion, RPM)? → add buyer posts to traffic-getting clusters.

## Monthly review (track + compare to milestone)
Published posts, Pinterest impressions/saves/outbound clicks, blog sessions, top posts, affiliate clicks +
conversion, ad revenue + RPM, net profit. Score vs the current milestone in `.claude/memory.md`.

## Output
A prioritized P1→P3 next-actions list, each mapped to the exact command to run. Lead with the top 3 moves.
