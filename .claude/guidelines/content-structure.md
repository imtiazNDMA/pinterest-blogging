# Guideline: Content Structure & Frontmatter

Every post is a Markdown file in `Content/` following this anatomy. The content-writer produces it; the
editor-qa checks it. Two intent types share the skeleton with small differences.

## Frontmatter (YAML, required)
```yaml
---
title: "Best Vegetables to Grow on a Balcony (Beginner's Guide)"
slug: best-balcony-vegetables-beginners
primary_keyword: "balcony vegetables for beginners"
secondary_keywords: ["easy balcony vegetables", "vegetables for small balcony", "container vegetables full sun"]
search_intent: informational        # informational | buyer
pillar: "Container & balcony how-tos"
cluster: "balcony-vegetables"
meta_description: "The easiest balcony vegetables for beginners, with pot sizes and sun needs for each — start your small-space garden with confidence."  # 140–160 chars
internal_links: ["best-pots-for-balcony", "balcony-vegetable-watering"]   # slugs to link to
monetized: true                     # true if affiliate links present
affiliate_programs: ["amazon", "true-leaf-market"]
status: draft                       # draft | ready | published
pin_batch_id: ""                    # filled by /make-pins
last_updated: 2026-06-24
---
```

## Body skeleton — INFORMATIONAL post
1. **Intro (2–4 sentences, no filler) — NO heading:** open with the paragraph itself; state the reader's problem + what they'll get. Primary keyword once.
2. **Quick answer / TL;DR block:** the short version up top (great for featured snippets + impatient pinners). Give it a *reader-facing* heading (e.g. "The short version", "The 5 best picks, ranked") — never the literal label "Quick answer".
3. **Main sections (H2s):** each a sub-question or step; specific (varieties, sizes, sun hours, timing).
   - Use tables for comparisons, numbered lists for steps.
   - One or two `[PERSONAL TIP: ...]` callout placeholders where lived experience would add most.
   - `[YOUR PHOTO: description]` placeholders where an original photo belongs (E-E-A-T + pin source).
4. **Common mistakes / "skip this if…"** (honesty = authority).
5. **FAQ (H2 + H3 questions):** mine PAA; 3–6 concise Q&As.
6. **Closing + internal links:** 1–2 sentences + "Next, read…" links to cluster siblings/pillar. Give it a *reader-facing* heading (e.g. "Start with one pot", "Your next step") — never the literal label "Wrap-up".

## Body skeleton — BUYER ("best X" / comparison) post
1. **Intro + FTC disclosure line** (above first affiliate link — required).
2. **Quick picks block:** "Best overall / Best budget / Best for tiny spaces" (qualitative, NO prices).
3. **Selection criteria (H2):** state HOW picks were chosen *before* listing them (kills thin-content flag).
4. **The picks (H2/H3 each):** what it is, who it's for, key features, trade-offs, qualitative value.
   Affiliate link with descriptive anchor. NO prices/stock/"cheapest".
5. **Comparison table** (features, not prices). Give it a *reader-facing* heading (e.g. "The picks compared at a glance") — never the literal label "Comparison table".
6. **How to choose / buying guide (H2):** decision helper.
7. **FAQ + wrap-up + internal links.**

## Rules of thumb
- **Headings are reader-facing, never scaffold labels.** "Intro", "Quick answer", "Wrap-up", and "Comparison table" are internal cues from the skeleton — never publish them as literal headings. The intro has NO heading; every other section gets a specific, reader-facing heading. (editor-qa greps for these and FAILs the draft if any leak through.)
- Lead with the answer; never bury it.
- Length follows intent, not a quota. Cut filler ruthlessly.
- Disclosure ABOVE first affiliate link on every monetized post.
- Minimum 3 internal links; descriptive anchors.
- Leave `[PERSONAL TIP]` / `[YOUR PHOTO]` placeholders — never auto-fill them.
