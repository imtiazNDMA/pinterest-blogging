# Content Generation Studio — Build Plan

_Draft plan for approval. Created 2026-06-24. Nothing is built yet; this file is the spec._

---

## 0. What we're building (the one-paragraph version)

A **`.claude/`-based content studio** that turns your strategy into repeatable, invokable machinery:
**7 specialized agents** (niche → keywords → content → editing → monetization → pins → analytics),
**~8 slash-command workflows** that orchestrate them, and a **knowledge base** of guardrails,
playbooks, guidelines, and templates that every agent reads so output is consistent, compliant,
and on-brand. You drive it with commands like `/new-post`; the studio produces publish-ready
Markdown drafts + Pinterest pin packages + a monetization and optimization loop.

---

## 1. Confirmed decisions (from this session)

| Decision | Choice | Consequence for the build |
|---|---|---|
| **Output pipeline** | Markdown drafts in repo (`Content/`) with YAML frontmatter | No WordPress API needed yet; git history of every draft; you paste into WP. A future `/publish` command can add REST API auto-draft. |
| **Draft depth** | Full drafts, minimal editing | Content-writer produces near-final posts. Editor/QA agent + content-quality guardrail stay in to prevent thin-AI penalties (studio self-checks, not extra work for you). |
| **Niche** | Re-open selection | Container gardening = leading candidate, NOT locked. Niche discovery/validation is the **first** workflow; niche-strategist is first-class & re-runnable. |
| **Pin images** | Copy + detailed Canva design briefs | Pinterest-strategist outputs titles/descriptions/board + a per-pin design brief (overlay text, colors, layout, image direction). You execute in Canva. |

---

## 2. Honest constraints & assumptions (these shape the design)

- **No logged-in tool access.** I can use WebSearch/WebFetch, but cannot reach Pinterest Trends,
  Google Keyword Planner, GA4, Search Console, or the Amazon dashboard. → The studio uses a
  **data-intake pattern**: agents do discovery + reasoning; you paste exports (Keyword Planner CSV,
  Pinterest Trends screenshots/exports, GA4/Pinterest analytics, Amazon reports); agents process them.
  Agents will **never invent search volumes** — they label numbers as "needs validation" until you supply data.
- **No image generation** in scope (per your choice). Pins = copy + briefs.
- **Amazon ToS / FTC are non-negotiable** and baked into guardrails (no live prices, required disclosure, etc.).
- **Existing assets are integrated, not duplicated:** `roadmap_codex.md` (strategic phases),
  `pinterest_blog_master_tracker.csv` (50-col tracker), `.claude/memory.md` (strategy). The studio
  reconciles `roadmap_codex.md` into the playbooks and uses the tracker as the system of record.
- **Bootstrap budget (<$30/mo)** respected throughout — free tools only.

---

## 3. Target `.claude/` directory structure

```
.claude/
├── CLAUDE.md                      # always-loaded: studio map + non-negotiable rules + brand voice
├── memory.md                      # (exists) strategy + monetization facts
├── agents/
│   ├── niche-strategist.md
│   ├── keyword-researcher.md
│   ├── content-writer.md
│   ├── editor-qa.md
│   ├── monetization-strategist.md
│   ├── pinterest-strategist.md
│   └── analytics-optimizer.md
├── commands/                      # workflows (slash commands)
│   ├── niche-research.md
│   ├── keyword-cluster.md
│   ├── new-post.md
│   ├── make-pins.md
│   ├── monetize-audit.md
│   ├── weekly-review.md
│   └── site-setup.md
├── guardrails/                    # hard rules agents must not violate
│   ├── affiliate-compliance.md    # FTC + Amazon Associates ToS
│   ├── content-quality.md         # anti-thin-AI, E-E-A-T, factual accuracy, YMYL/plant-pet-safety
│   ├── seo-rules.md               # 1 primary kw/post, structure, no stuffing, internal links
│   └── pinterest-policy.md        # fresh pins, 2:3, anti-spam, no misleading pins
├── playbooks/                     # step-by-step repeatable procedures
│   ├── niche-validation.md
│   ├── keyword-research.md
│   ├── topic-cluster.md
│   ├── content-production.md
│   ├── pin-creation.md
│   ├── monetization.md            # affiliate ladder, product selection, ad-network timing
│   ├── analytics-optimization.md
│   └── site-setup.md
├── guidelines/                    # specs & standards (the "what good looks like")
│   ├── brand-voice.md
│   ├── content-structure.md       # post anatomy + frontmatter schema
│   ├── pin-spec.md                # angle taxonomy + copy formulas + design spec
│   ├── cluster-schema.md
│   ├── tracker-schema.md          # how to read/write the master CSV
│   └── naming-conventions.md      # file & folder naming, slugs
└── templates/                     # fill-in-the-blank starting points
    ├── content-brief.md
    ├── post-skeleton.md           # frontmatter + section skeleton
    ├── pin-batch.md
    ├── niche-scorecard.md
    └── cluster-map.md
```

---

## 4. The 7 specialized agents

Each agent = its own context window + system prompt + tool set. All read the relevant
guardrails/guidelines automatically.

1. **niche-strategist** — Discovers & scores candidate niches against your interests
   (gardening, decor/organization, crafts/DIY, pets) on 6 axes: Pinterest visual demand,
   evergreen search depth, Amazon product intent, ad-friendly informational volume, competition,
   cluster-expansion room. Output: scored **niche scorecard** + recommendation. Re-runnable on pivot.
   _Tools: WebSearch, WebFetch, Read, Write._

2. **keyword-researcher** — Takes a pillar/topic → produces validated keyword clusters: seed
   expansion (Pinterest + Google autocomplete, PAA, related searches), intent tagging
   (informational vs buyer), long-tail mapping, difficulty estimate, and a **content brief** per post.
   Flags all volume numbers as "needs validation" unless you supply tool exports. Logs to `keyword Research/`.
   _Tools: WebSearch, WebFetch, Read, Write._

3. **content-writer** — Turns a brief into a full, publish-ready Markdown post (frontmatter +
   intro + scannable H2/H3 + natural product mentions + disclosure + internal-link placeholders +
   optional `[YOUR PHOTO]`/`[PERSONAL TIP]` hooks). Follows brand-voice + content-structure + SEO rules.
   _Tools: Read, Write, WebSearch (for fact-checking)._

4. **editor-qa** — Adversarial reviewer. Audits a draft against content-quality + affiliate +
   SEO guardrails: thin/generic-AI smell test, intent satisfaction, factual & plant/pet-safety accuracy,
   disclosure placement, keyword usage, readability, internal links. Returns a pass/fail checklist + fixes.
   _Tools: Read, Edit, WebSearch._

5. **monetization-strategist** — Affiliate program research (Amazon + higher-rate garden programs),
   product selection for buyer posts (with selection criteria, not scraped prices), affiliate placement
   review, and **ad-network readiness audits** (AdSense / Mediavine Journey @1k sessions / Raptive @25k).
   _Tools: WebSearch, WebFetch, Read, Write._

6. **pinterest-strategist** — For a post, generates a pin batch: N pins across the angle taxonomy
   (search/curiosity/product/budget/beginner/seasonal), each with keyword-rich title, natural
   description, board assignment, and a **Canva design brief**. Plus a spaced pinning schedule.
   _Tools: Read, Write._

7. **analytics-optimizer** — Ingests the tracker CSV + any pasted GA4/Pinterest/Amazon exports →
   surfaces winners/losers, posts to refresh, pin designs to kill, clusters to expand, and a
   prioritized next-actions list. Drives the optimization loop.
   _Tools: Read, Write, WebSearch._

---

## 5. The workflows (slash commands)

| Command | What it does | Agents it calls |
|---|---|---|
| `/niche-research` | Discover + score candidate niches → finalize one | niche-strategist |
| `/keyword-cluster <topic>` | Build a validated keyword cluster + per-post briefs | keyword-researcher |
| `/new-post <keyword\|brief>` | brief → draft → QA → product insert → save to `Content/` → log tracker | keyword-researcher → content-writer → editor-qa → monetization-strategist |
| `/make-pins <post>` | Generate a pin batch + design briefs + schedule → log tracker | pinterest-strategist |
| `/monetize-audit` | Affiliate-program gaps, product opportunities, ad-network readiness | monetization-strategist |
| `/weekly-review` | Ingest metrics → winners/losers → prioritized next actions | analytics-optimizer |
| `/site-setup` | Checklist-driven WordPress + Pinterest + trust-pages setup guide | (playbook-driven) |

---

## 6. End-to-end content flow (how a post is born)

```
/niche-research ──► finalize niche
        │
/keyword-cluster "balcony vegetables" ──► cluster map + 6–10 briefs ──► keyword Research/ + tracker (Idea)
        │
/new-post <brief> ──► content-writer draft ──► editor-qa pass ──► monetization product insert
        │                                                              │
        └──► Content/<slug>.md (publish-ready) + tracker (Draft→Ready)  │
        │
/make-pins <slug> ──► 4–8 pins + Canva briefs + schedule ──► tracker (Pin rows)
        │
[you] publish to WordPress + design pins in Canva + schedule
        │
/weekly-review ──► analytics-optimizer ──► refresh/expand/kill decisions ──► loop
```

---

## 7. Guardrails (the non-negotiables, summarized)

- **affiliate-compliance:** FTC disclosure above the first affiliate link on every monetized post;
  required Amazon Associates disclosure text; **no live prices / "cheapest" / availability claims**
  (Amazon ToS); no fabricated reviews; affiliate links only where genuinely helpful.
- **content-quality:** anti-thin-AI checklist; every post must add original angle/selection criteria;
  factual accuracy with sources; **plant & pet safety must be correct** (toxicity, edibility) — no guessing;
  no fabricated personal experience (experience hooks are optional placeholders for *you* to fill).
- **seo-rules:** one primary long-tail keyword/post; title + meta + H-structure spec; satisfy intent fully;
  ≥3 internal links; no keyword stuffing; descriptive image alt/filenames.
- **pinterest-policy:** fresh pins only (new image/design per pin); strict 2:3 (1000×1500); keyword-rich
  but non-spammy titles/descriptions; pins must match destination (no misleading); spaced cadence.

---

## 8. Build phases (staged for your review)

- **Phase A — Foundation:** `CLAUDE.md` (studio map + rules + brand voice) + all `guidelines/` + `guardrails/`.
  _This is the shared brain; everything else references it. You review before agents are built._
- **Phase B — Agents:** the 7 `agents/*.md`.
- **Phase C — Workflows:** the 7 `commands/*.md` + `playbooks/`.
- **Phase D — Templates** + reconcile `roadmap_codex.md` + tracker schema doc.
- **Phase E — First live run:** execute `/niche-research` to validate/lock the niche, then `/keyword-cluster`.

After each phase I pause for your check. (We can compress phases if you'd rather move fast.)

---

## 9. Decisions (resolved 2026-06-24)

1. **Brand voice:** Friendly **second-person ("you")** coaching tone. Authority comes from specificity +
   original selection criteria + accurate plant/pet safety, with optional first-person `[PERSONAL TIP]` callouts.
2. **Pin tool:** **Canva free** for design + **Pinterest native scheduler** (free) for cadence.
3. **Build pace:** **One pass**, then full review.
4. **`roadmap_codex.md`:** **Fold into playbooks, then retire** the standalone file (single source of truth).
5. **Blog name:** none yet → use placeholder `{{BLOG_NAME}}` / `{{DOMAIN}}` tokens everywhere so it's a find-replace later.

---

## 10. First action after approval

Build **Phase A** (CLAUDE.md + guidelines + guardrails) and show it to you — the foundation every
agent depends on — then proceed through B–E.
