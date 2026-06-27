# Pinterest Blogging Project — Balcony & Patio Styling

A content-production system for a Pinterest-fed, SEO-durable, monetized blog in the **Balcony & Patio Styling**
niche (decor-led styling of small balconies and patios). Niche committed 2026-06-25. Brand not chosen yet →
the tokens `Bloom & Lantern`, `https://bloomandlantern.com`, `{{AMAZON_TAG}}` are placeholders, find-replaced once decided.

This repo is organized into **three layers** that do different jobs.

---

## The three layers

### 1. 🏭 Studio — `.claude/` (production)
The engine that *makes* the content. Specialist subagents, slash-command workflows, and non-negotiable
guardrails turn one keyword into a publish-ready post + a fresh-pin batch.

- `agents/` — 7 specialists (niche, keyword, writer, editor/QA, monetization, pinterest, analytics)
- `commands/` — slash-command workflows (`/new-post`, `/make-pins`, `/keyword-cluster`, `/weekly-review`, …)
- `guardrails/` — hard rules (anti-AI-slop, content-quality, SEO, affiliate compliance, Pinterest policy, AI-image)
- `guidelines/` — specs/standards (brand voice, structure, formatting, pin visual style, tracker schema, …)
- `playbooks/` — repeatable procedures (content production, pin design + image generation, editing/de-slop, …)
- `templates/` — fill-in starting points (post skeleton, content brief, pin batch, AI image prompts, …)
- `CLAUDE.md` — the studio map + the short list of non-negotiable rules. **Read it first.**

### 2. 🧭 Vault — `Blog Vault/` (planning, tracking, motivation)
An **Obsidian vault** (open the folder as a vault) to *run* the business: goals, milestones, income, content
calendar, Pinterest plan, analytics, SOPs. Plugin-free; cross-linked with `[[wikilinks]]`. Start at
`Blog Vault/Home.md`. Pre-filled with the real current state.

### 3. 📝 Content & research (the output + the inputs)
- `Content/` — finished, publish-ready Markdown post drafts (paste into WordPress). `Content/pins/` holds the pin batches.
- `keyword Research/` — keyword clusters + the Pinterest demand-validation data (`_validation-volumes-*.md`).
- `niche research/` — niche discovery, scoring, and the final niche analysis.
- `Growth Strategy/` — higher-level strategy notes.
- `docs/` — specs/plans for studio changes.

---

## System of record
`pinterest_blog_master_tracker.csv` (repo root) is the **single source of truth** — every post and pin gets a
row. If it isn't in the CSV, it doesn't exist. Schema + the strict CSV-quoting rules live in
`.claude/guidelines/tracker-schema.md`. The Vault's trackers are the human-friendly mirror of this CSV.

## The pipeline (one post, end to end)
```
/keyword-cluster <topic>   → cluster + per-post briefs  → keyword Research/ + tracker
/new-post <brief>          → draft → QA → monetize       → Content/<slug>.md + tracker
/make-pins <slug>          → fresh-pin batch + schedule  → Content/pins/<slug>-pins.md + tracker
[you] publish + design pin images (studio gives briefs + plug-and-play AI prompts)
/weekly-review             → ingest metrics → optimize   → loop
```

## Current state (as of 2026-06-26)
- **5 posts READY** (cozy, budget, renter, makeover, + the pillar hub) — pending owner inputs (real photos,
  affiliate links, `[PERSONAL TIP]`, token replacement).
- **25 pins designed** (PB-001 → PB-005), scheduled 06-26 → 07-20.
- **Cluster validated** with real Pinterest volumes; next post = **Balcony Privacy** (20k).
- **Not live yet** — building the content backlog before launch.

## Ground rules (full text in `.claude/guardrails/`)
1. FTC disclosure above the first affiliate link. 2. No Amazon prices / "cheapest" / stock claims. 3. No
fabricated experience, reviews, or data. 4. Plant/pet safety verified (YMYL). 5. One primary keyword per post,
intent satisfied, ≥3 internal links. 6. Fresh pins only, strict 2:3 (1000×1500), label AI honestly. 7. Bootstrap
budget (free tools unless approved). 8. Log everything to the tracker.

## Quick start
- **To produce content:** read `.claude/CLAUDE.md`, then run the pipeline commands above.
- **To plan & track:** open `Blog Vault/` in Obsidian, start at `Home.md`.
- **To publish:** fill owner inputs on a READY post in `Content/`, replace tokens, paste into WordPress.
