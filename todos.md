# Build Journal & TODO — Bloom & Lantern

> **Purpose:** the studio's living task tracker + journey log. This is the human checklist;
> `pinterest_blog_master_tracker.csv` stays the system of record for posts/pins.
> **Rule:** update after each work block — check boxes, add a dated line to the Journey log.
> Brand: **Bloom & Lantern** / `https://bloomandlantern.com` — domain + **Stellar Plus** hosting
> purchased 2026-06-27 (Namecheap). Brand/domain tokens find-replaced repo-wide 2026-06-27;
> only `{{AMAZON_TAG}}` (Associate tag) and `{{CONTACT_EMAIL}}` remain to fill.

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

### 🤖 Claude builds — status
- [x] **Trust/legal page drafts** — About · Affiliate Disclosure · Privacy → `Content/pages/` (committed). Owner fills `{{CONTACT_EMAIL}}` + run Privacy through Termly/iubenda before launch.
- [x] **Pin batch PB-007** — planters post (Rec 4) → `Content/pins/best-self-watering-planters-balcony-pins.md` (5 fresh pins). **Logged 5 Pin rows (PB-007, Rec 58–62) to the tracker 2026-06-27.** ✅
- [x] **Patio hub post** — `small patio ideas` (118k) → `Content/small-patio-ideas.md` (Rec 47). **Written 2026-06-27** via full `/new-post` pipeline (brief → content-writer → monetization → editor-qa). ~2,150 words, 30 ideas, 18 internal links, light monetization block, editor-qa PASS all gates → **status=Ready**. Owner: pick SEO title, fill 1 [PERSONAL TIP] + 5 [YOUR PHOTO].
- [x] **Pin batch PB-008** — patio hub (Rec 47) → `Content/pins/small-patio-ideas-pins.md` (5 fresh pins, distinct archetypes). **Logged 5 Pin rows (PB-008, Rec 63–67) to the tracker 2026-06-27**; scheduled 2026-07-31 → 08-04. Owner: design in Canva (2:3 1000×1500), label AI, schedule via Pinterest native scheduler. ✅
- [x] **Patio furniture MONEY post** — `patio furniture ideas` (30k, buyer) → `Content/patio-furniture-ideas.md` (Rec 54). **Written 2026-06-27** via full `/new-post` pipeline. ~1,650 words, 7 distinct best-for picks (Wayfair-anchor + Amazon-support), 6 internal links (fills the hub's "patio furniture ideas for tight spaces" down-link), no-price comparison table, editor-qa PASS all gates → **status=Ready**. Owner: pick SEO title, fill 1 [PERSONAL TIP] + 5 [YOUR PHOTO], swap affiliate placeholders. ✅
- [x] **Pin batch PB-009** — patio furniture post (Rec 54) → `Content/pins/patio-furniture-ideas-pins.md` (5 fresh pins: hero / 6-type grid / wicker-vs-iron-vs-metal / foldable / layout diagram). **Logged 5 Pin rows (PB-009, Rec 68–72) to the tracker 2026-06-27**; scheduled 2026-08-05 → 08-09. A/B retarget test noted ("Best Small-Patio Furniture" vs gallery hero). Owner: design in Canva (2:3 1000×1500), label AI, schedule via Pinterest native scheduler. ✅
- [x] **Patio garden HUB post** — `patio garden ideas` (63k, P2 garden sub-hub) → `Content/patio-garden-ideas.md` (Rec 52). **Written 2026-06-27** via full `/new-post` pipeline. ~1,680 words, ~28 ideas, 7 internal links (fills the hub's "build a small patio garden" down-link), light monetization block. **YMYL: petunia/zinnia/sunflower pet-safe claims ASPCA-verified (cats + dogs); marigold omitted as cat-toxic.** editor-qa PASS all gates → **status=Ready**. Owner: pick SEO title, fill 1 [PERSONAL TIP] + 5 [YOUR PHOTO], swap affiliate placeholders. Next: `/make-pins patio-garden-ideas`. ✅

### 🏗️ At the office — Buy + set up (owner actions)
- [x] **Buy `bloomandlantern.com`** — purchased 2026-06-27 (Namecheap). Confirm auto-renew + WHOIS privacy on.
- [x] **Buy hosting** — **Stellar Plus** (Namecheap) purchased 2026-06-27.
- [x] **Token find-replace pass** — `Bloom & Lantern` / `https://bloomandlantern.com` applied repo-wide 2026-06-27 (43 files; `{{AMAZON_TAG}}` + `{{CONTACT_EMAIL}}` still tokens).
- [ ] **Install WordPress on Stellar Plus** — via cPanel/Softaculous; free fast theme (Kadence/GeneratePress); permalinks `/%postname%/`; point `bloomandlantern.com` to the host (auto on Namecheap). Run `/site-setup` for the full walkthrough.
- [ ] **WordPress baseline** — install plugins (Rank Math SEO, caching, image optimization, ToC); connect GA4 + Search Console; submit sitemap
- [ ] Set **GitHub repo → private** (`gh repo edit imtiazNDMA/pinterest-blogging --visibility private` or repo Settings → Danger Zone)

### 🔑 At the office — Brand + keyword (owner actions)
- [ ] Trademark sanity check — USPTO TESS, "bloom and lantern"
- [ ] Claim `@bloomandlantern` on **Pinterest** + **Instagram** (fallback: `@bloomandlanternco`)
- [ ] **Export `small backyard ideas`** from PinClicks → drop in `keyword Research/` → tell Claude "process these" (closes the keyword map)

---

## 📋 Up next (queued — not today)
- [ ] **Keyword frontier → backyard:** export `small backyard ideas` from PinClicks → drop in `keyword Research/` → "process these"
- [ ] Then patio long-tail: `back patio ideas`, `mini patio ideas`, `patio conversation set` (buyer); plus dedicated seasonal + lighting seeds (came back empty in topic exports)
- [ ] **Content backlog (money-weighted):** apartment-balcony-decorating (69k) · modern (57k) · boho (16k) · then patio cluster: small patio ideas (118k hub) → patio garden (63k) → patio furniture (money)
- [ ] **Resume PARKED automation redesign:** make CSV the single source of truth + auto-regenerate vault. Decided: data-pages generated / prose-pages manual. Next decision: sync mechanism (`/sync-vault` command vs hooks)
- [ ] Pre-launch owner inputs on the 6 READY posts: real photos, `[PERSONAL TIP]`, real affiliate links, replace tokens
- [x] `/site-setup` run 2026-06-27 → master checklist at `Growth Strategy/setup-checklist.md` (Stellar Plus install steps, Pinterest boards, GA4/GSC, publish order). Owner now executes the install + Pinterest + analytics steps.

---

## 🗺️ Journey log (milestones)
- **2026-06-27 (later)** — **Domain `bloomandlantern.com` + Stellar Plus hosting purchased** (Namecheap). Ran the brand/domain **token find-replace repo-wide** (43 files): `{{BLOG_NAME}}`→Bloom & Lantern, `{{DOMAIN}}`→`https://bloomandlantern.com`; `{{AMAZON_TAG}}` kept. Built out patio space: **hub (Rec 47)**, **furniture money post (Rec 54)**, **garden hub (Rec 52)** all READY, with pin batches **PB-008/009** logged. Next: install WordPress on Stellar Plus, then `/site-setup`.
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
