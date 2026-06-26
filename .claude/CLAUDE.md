# Pinterest Gardening Blog — Content Studio

This repo is a **content production studio**. Its job: turn one niche into a repeatable engine of
Pinterest-driven, SEO-durable, monetized blog content. Read this file first; it maps the studio and
states the rules every agent and command must obey.

> Project context lives in `.claude/memory.md` (strategy + 2026 monetization facts). Read it for the
> "why." This file is the "how."

---

## Current state (update as it changes)
- **Niche:** **Balcony & Patio Styling** — *committed 2026-06-25* via `/niche-research` (71/85). Decor-led styling of small balconies/patios (furniture, lights, layouts), bridging home decor × gardening. Container gardening = future expansion arm. Full analysis: `niche research/research.md`.
- **Production mode:** **AI-for-everything** — AI-generated articles, pins, and images. Moat = depth + specificity + scannable formatting (content-craft guardrails), not faked anecdotes. Label AI honestly on Pinterest (home-decor GenAI opt-out).
- **Brand name:** not chosen → use the token `{{BLOG_NAME}}` and `{{DOMAIN}}` everywhere; find-replace later.
- **Voice:** friendly **second person ("you")**. See `guidelines/brand-voice.md`.
- **Output:** publish-ready **Markdown** drafts in `Content/`; you paste into WordPress. No site live yet.
- **Pins:** copy + **AI-generated images** (with Canva design briefs as fallback), Pinterest native scheduler. Label AI on Pinterest.
- **System of record:** `pinterest_blog_master_tracker.csv` (see `guidelines/tracker-schema.md`).

---

## How the studio is organized

| Folder | What's in it | When it's used |
|---|---|---|
| `agents/` | 7 specialist subagents (niche, keyword, writer, editor, monetization, pinterest, analytics) | Dispatched by commands or directly |
| `commands/` | Slash-command workflows that orchestrate agents | You invoke them (`/new-post`, etc.) |
| `guardrails/` | **Non-negotiable rules** — compliance, quality, SEO, Pinterest | Every relevant agent must read + obey |
| `playbooks/` | Step-by-step repeatable procedures | Agents/commands follow them |
| `guidelines/` | Specs & standards (voice, structure, schemas) | "What good looks like" |
| `templates/` | Fill-in starting points (briefs, post skeleton, pin batch) | Copied, not edited in place |

### The pipeline (one post, end to end)
```
/niche-research → finalize niche
/keyword-cluster <topic> → cluster + per-post briefs → keyword Research/ + tracker
/new-post <brief>  → draft → QA → product insert → Content/<slug>.md + tracker
/make-pins <slug>  → pin batch + Canva briefs + schedule → tracker
[you] publish + design pins
/weekly-review → optimize → loop
```

---

## Non-negotiable rules (the short list — full text in `guardrails/`)

1. **Disclose affiliations.** Every post with affiliate links carries an FTC disclosure *above the first
   affiliate link*. See `guardrails/affiliate-compliance.md`.
2. **Never state Amazon prices, "cheapest," or stock status.** Amazon ToS. Describe value qualitatively.
3. **Never fabricate experience, reviews, or data.** No invented search volumes, no fake "I tested this."
   Personal claims live only in `[PERSONAL TIP]` placeholders **you** fill. See `guardrails/content-quality.md`.
3b. **No AI slop.** Banned phrasings, generic prose, and structural tells fail the `guardrails/anti-ai-slop.md`
   kill pass — a slop draft does not ship. Titles/hooks/CTAs follow the craft guidelines (`guidelines/headlines-and-titles.md`,
   `hooks-and-intros.md`, `conversion-copywriting.md`).
4. **Plant & pet safety must be correct.** Toxicity, edibility, and care claims are verified, not guessed.
   This is YMYL-adjacent — when unsure, hedge and cite.
5. **One primary keyword per post; satisfy intent fully; ≥3 internal links; no keyword stuffing.**
   See `guardrails/seo-rules.md`.
6. **Fresh pins only, strict 2:3 (1000×1500), no misleading pins.** See `guardrails/pinterest-policy.md`.
   AI images obey `guardrails/ai-image-generation.md` (authentic, no logos/prices/garbled text, **label AI**);
   design system in `guidelines/pin-visual-style.md`, prompts in `templates/ai-image-prompt.md`, procedure in
   `playbooks/pin-image-generation.md`.
7. **Bootstrap budget:** free tools only unless I explicitly approve a cost.
8. **Log everything to the tracker.** A post/pin that isn't in the CSV doesn't exist.

---

## Conventions
- **Tokens:** `{{BLOG_NAME}}`, `{{DOMAIN}}`, `{{AMAZON_TAG}}` are placeholders — never hard-code a real value until I provide it.
- **Files & slugs:** see `guidelines/naming-conventions.md`.
- **Data intake:** I cannot log into Pinterest Trends / Keyword Planner / GA4 / Search Console / Amazon.
  When real numbers are needed, I produce the structure and you paste exports; I then process them.
  Estimated numbers are always labeled `(est — needs validation)`.
- **When a guardrail and a request conflict,** surface the conflict; do not silently violate a guardrail.
