# Guideline: Naming Conventions & File Layout

## Project folders (repo root)
```
Content/              # publish-ready post drafts: <slug>.md
keyword Research/     # one file per cluster: <cluster-slug>.md (+ optional .csv)
niche research/       # niche scorecards + validation reports
Growth Strategy/      # calendars, monetization plans, ad-network readiness docs
pinterest_blog_master_tracker.csv   # system of record
.claude/              # the studio (agents, commands, guardrails, playbooks, guidelines, templates)
```

## Slugs (posts, pins, clusters)
- lowercase, hyphen-separated, no stop-word padding: `best-balcony-vegetables-beginners`.
- Keyword-led; ≤ ~60 chars; ASCII only.
- Cluster slug = the head term: `balcony-vegetables`.

## File names
- **Post draft:** `Content/<slug>.md`.
- **Cluster keyword file:** `keyword Research/<cluster-slug>.md`.
- **Niche scorecard:** `niche research/<niche-slug>-scorecard.md`; comparison: `niche research/niche-comparison-YYYY-MM-DD.md`.
- **Pin batch:** stored inline with the post or `Content/pins/<slug>-pins.md`; `Pin Batch ID` = `PB-###` (PB-001, PB-002…).
- **Image filenames (for the user to use):** `<slug>-<descriptor>.jpg`, e.g. `balcony-vegetables-cherry-tomatoes.jpg`.

## IDs
- **Pin Batch ID:** `PB-###`, sequential.
- **Record ID** (tracker): integer, sequential, never reused.

## Tokens (never hard-code real values)
- `{{BLOG_NAME}}` — blog/brand name (not chosen yet).
- `{{DOMAIN}}` — site domain, no protocol (e.g. `examplegarden.com`).
- `{{AMAZON_TAG}}` — Amazon Associates tracking ID.
Replace via find-and-replace once the user provides them.

## Dates
- ISO 8601 `YYYY-MM-DD` everywhere.
