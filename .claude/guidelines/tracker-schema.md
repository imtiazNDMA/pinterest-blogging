# Guideline: Master Tracker Schema

`pinterest_blog_master_tracker.csv` (repo root) is the **system of record**. Every post and pin gets a row.
Agents read it for state and append/update rows; the analytics-optimizer reads it to find winners.

## Row types (`Record Type` column)
- **Content** — one row per blog post.
- **Pin** — one row per individual pin (linked to a post via the same `Cluster/Niche` + `Post Title` and a `Pin Batch ID`).
- **Monthly Summary** — one row per month for roll-up metrics (sessions, RPM, revenue).

The seed CSV ships 3 `Example *` rows — these are templates; real rows drop the "Example" prefix.

## Column groups (51 columns)
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

> **Fallback:** the commands above are the normal loggers, but agents (content-writer, editor-qa,
> pinterest-strategist) dispatched **directly** must log their own row here, or end their output with a
> loud `⚠ TRACKER NOT LOGGED — …` line. A post/pin not in the CSV doesn't exist (CLAUDE.md rule 8).

## Rules
- **Numbers only from real exports.** Never fabricate metrics; leave blank until data exists.
- Keep one source of truth — don't fork the CSV. Edits are appends/updates in place.
- Metric columns the user can't yet provide stay empty (not zero) to avoid skewing analysis.
- Dates ISO `YYYY-MM-DD`.

## CSV-safety (HARD — prevents row corruption)
Free-text fields routinely contain commas (**Notes**, **Next Action**, **Pin Title**, descriptions). A
comma that isn't inside quotes **silently splits the row** into extra fields and breaks column alignment for
every downstream metric. This has bitten the tracker before. So:
- **Wrap every free-text field that could contain a comma, double-quote, or newline in double quotes.**
  Escape any internal `"` by doubling it (`"` → `""`). When in doubt, quote the field.
- **Every row has exactly 51 comma-separated fields** — no more, no fewer.
- **Verify after writing.** Re-parse the row (or the file) with a real CSV parser and confirm 51 fields per
  row. A quick check: `python -c "import csv; print({len(r) for r in csv.reader(open('pinterest_blog_master_tracker.csv',encoding='utf-8',newline=''))})"`
  must print `{51}`. If it doesn't, you split a row — fix it before finishing.
- **Prefer a CSV writer over hand-built strings.** Don't paste raw free text straight into a comma-joined
  line; let a CSV library quote it, or quote it yourself per the rule above. Avoid unescaped newlines in a cell.
- **Preserve EVERY row — never write a subset.** To update one row you must read the WHOLE file, change only
  your row, and write back **all** rows. **Verify the row count did not drop** (it should be unchanged on an
  update, or +N on an append) — e.g. `python -c "import csv; print(sum(1 for _ in csv.reader(open('pinterest_blog_master_tracker.csv',encoding='utf-8',newline=''))))"`.
  A partial rewrite silently deletes pin/post rows (this has happened — 29 rows were lost once and recovered from git).
