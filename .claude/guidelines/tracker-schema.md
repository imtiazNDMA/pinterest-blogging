# Guideline: Master Tracker Schema

`pinterest_blog_master_tracker.csv` (repo root) is the **system of record**. Every post and pin gets a row.
Agents read it for state and append/update rows; the analytics-optimizer reads it to find winners.

## Row types (`Record Type` column)
- **Content** — one row per blog post.
- **Pin** — one row per individual pin (linked to a post via the same `Cluster/Niche` + `Post Title` and a `Pin Batch ID`).
- **Monthly Summary** — one row per month for roll-up metrics (sessions, RPM, revenue).

The seed CSV ships 3 `Example *` rows — these are templates; real rows drop the "Example" prefix.

## Column groups (50 columns)
- **Identity:** Record ID, Record Type, Cluster/Niche, Post Title, Post URL, Primary Keyword, Search Intent.
- **Content lifecycle:** Content Status (Idea→Outline→Draft→Ready→Published), Draft Start/Publish/Last-Updated dates, Word Count.
- **Monetization on-page:** Affiliate Links Added, Amazon Products Featured, Disclosure Added, Internal Links Added.
- **Pins:** Pin Batch ID, Pin Title, Pin URL, Pin Design Angle, Pin Publish Date, Pinterest Board, Pin Status.
- **Pinterest metrics:** Impressions, Saves, Outbound Clicks, CTR.
- **Google metrics:** Google Impressions, Clicks, CTR.
- **Site metrics:** Blog Sessions, Pageviews, Avg Time on Page, Email Signups.
- **Amazon:** Clicks, Ordered Items, Shipped Items, Revenue, Commission.
- **Ads:** Ad Network, Ad Sessions, Ad RPM, Ad Revenue.
- **Other affiliate:** Network, Clicks, Revenue.
- **Roll-up:** Total Revenue, Estimated Cost, Net Profit, Notes, Next Action.

## Who writes what
- **keyword-researcher / `/keyword-cluster`:** creates `Content` rows at status `Idea` (Cluster, Title, Primary Keyword, Intent, Next Action).
- **`/new-post`:** flips Content Status `Draft`→`Ready`, fills Word Count, Disclosure/Internal/Affiliate flags, Post URL when known.
- **pinterest-strategist / `/make-pins`:** appends `Pin` rows (Batch ID, Title, Angle, Board, Status=Draft → scheduled date).
- **analytics-optimizer / `/weekly-review`:** fills metric columns from pasted exports, computes CTR/RPM/Net Profit, sets Next Action.

## Rules
- **Numbers only from real exports.** Never fabricate metrics; leave blank until data exists.
- Keep one source of truth — don't fork the CSV. Edits are appends/updates in place.
- Metric columns the user can't yet provide stay empty (not zero) to avoid skewing analysis.
- Dates ISO `YYYY-MM-DD`.
