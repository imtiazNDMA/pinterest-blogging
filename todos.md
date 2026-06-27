# Build Journal & TODO — Bloom & Lantern

> **Purpose:** the studio's living task tracker + journey log. This is the human checklist;
> `pinterest_blog_master_tracker.csv` stays the system of record for posts/pins.
> **Rule:** update after each work block — check boxes, add a dated line to the Journey log.
> Brand chosen: **Bloom & Lantern** / `bloomandlantern.com` (domain purchase pending → tokens
> `{{BLOG_NAME}}`/`{{DOMAIN}}` stay until bought).

---

## 🎯 Today — 2026-06-27

### Done
- [x] Push repo to GitHub remote (`origin/main`, imtiazNDMA/pinterest-blogging)
- [x] Inventory all keyword research + write `keyword Research/suggestions.md` (PinClicks expansion method + frontier)
- [x] Process 6 patio PinClicks exports → validate **Patio** as a 2nd space (+2,606 terms; dataset 4,413 / 7.84M SV)
- [x] Fold patio pillar into tracker (12 Idea rows), master plan (`.claude/memory.md`), `.claude/CLAUDE.md`, vault strategy pages
- [x] Generate + RDAP-verify 10 available brand/domain names
- [x] Choose brand: **Bloom & Lantern** → `bloomandlantern.com` (verified available)
- [x] Save session to memory + update this tracker

### At the office (owner actions — only you can do)
- [ ] **Buy `bloomandlantern.com`** — confirm standard (not premium) price; enable auto-renew + free WHOIS privacy
- [ ] Trademark sanity check — USPTO TESS, "bloom and lantern"
- [ ] Claim `@bloomandlantern` on **Pinterest** + **Instagram** (fallback: `@bloomandlanternco`)
- [ ] Decide GitHub repo visibility — **public vs private** (it holds tracker/strategy/vault)
- [ ] After purchase → tell Claude to run the `{{BLOG_NAME}}`/`{{DOMAIN}}` find-replace pass

---

## 📋 Up next (queued — not today)
- [ ] **Keyword frontier → backyard:** export `small backyard ideas` from PinClicks → drop in `keyword Research/` → "process these"
- [ ] Then patio long-tail: `back patio ideas`, `mini patio ideas`, `patio conversation set` (buyer); plus dedicated seasonal + lighting seeds (came back empty in topic exports)
- [ ] **Content backlog (money-weighted):** apartment-balcony-decorating (69k) · modern (57k) · boho (16k) · then patio cluster: small patio ideas (118k hub) → patio garden (63k) → patio furniture (money)
- [ ] **Resume PARKED automation redesign:** make CSV the single source of truth + auto-regenerate vault. Decided: data-pages generated / prose-pages manual. Next decision: sync mechanism (`/sync-vault` command vs hooks)
- [ ] Pre-launch owner inputs on the 6 READY posts: real photos, `[PERSONAL TIP]`, real affiliate links, replace tokens
- [ ] `/site-setup` when ready to go live (WordPress + Pinterest business + trust pages)

---

## 🗺️ Journey log (milestones)
- **2026-06-27** — Repo pushed to GitHub. Built keyword-expansion method (`suggestions.md`). **Patio validated as a full 2nd space** (+2,606 terms; hub "small patio ideas" 118k) and folded into tracker/plan/vault. **Brand chosen: Bloom & Lantern** (`bloomandlantern.com`, verified available). Next frontier = backyard.
- **2026-06-26** — Validated demand with 10 PinClicks sheets (1,807 terms). 6 posts READY; 30 pins designed (PB-001→006); built the Obsidian `Blog Vault/` (24 notes). 6 pillars + WP categories confirmed; Lighting restored to P2.
- **2026-06-25** — **Niche COMMITTED: Balcony & Patio Styling.** All 6 post-stress-test studio fixes applied; content-craft guardrails added (formatting/humanization/anti-slop); studio versioned in git.
- **2026-06-24** — Built the content studio in `.claude/` (7 agents, 7 commands, guardrails/guidelines/playbooks/templates). Ran `/new-post` stress test → surfaced the 6 fixes (archived below).

---

## 📦 Archive — Studio fixes (2026-06-24 stress test) — ✅ all done 2026-06-25

> Kept for the record. Sample post `Content/best-self-watering-planters-balcony.md` (tracker Record ID 4).

- [x] **1. (High) Scaffolding headings leak into posts** — cues moved to HTML comments in `post-skeleton.md`; `content-structure.md` rule; `editor-qa` greps bare scaffold headings.
- [x] **2. (Med) Too few `[YOUR PHOTO]` markers** — `content-writer` now requires 2–4 (one/pin angle); `editor-qa` FAILs if <2.
- [x] **3. (Med) "Best for…" segments not distinct** — `conversion-copywriting.md` requires distinct product categories.
- [x] **4. (Low) No year-in-title policy** — `headlines-and-titles.md`: default no year in SEO title/H1/slug.
- [x] **5. (Med) Tracker logging orchestration-only** — `/new-post` step 5 explicit; agents got a tracker-logging fallback.
- [x] **6. (Low) Ambiguous H2 keyword rule** — `seo-rules.md`: primary keyword OR close variant in ≥1 H2.
- [x] **Content-craft guardrails** — `formatting-and-readability.md` + `humanization.md`; anti-slop bans arrows/emoji; deeper `conversion-copywriting.md`; emoji ban in pins; wired into `content-writer` + `editor-qa`.
- [x] **Sample post brought into compliance** — dashes 39→0, scaffold headings removed, duplicate pick fixed, year stripped, photo markers 1→2, tracker row 4 → Ready.
- [x] **Studio committed to git** — re-initialized `.git`, one commit per fix on `main`.
