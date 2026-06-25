# Guardrail: Content Quality (anti-thin-AI, E-E-A-T, accuracy)

**Status: hard rules.** This is the firewall against the generic-AI content that Google sandboxes and
Pinterest throttles. "Full drafts, minimal editing" only works if every draft clears this bar.

> **Deep AI-tell detection lives in `anti-ai-slop.md`** (banned phrasings, structural tells, the de-slop kill
> pass). This file covers the broader quality bar — E-E-A-T, accuracy, structure. editor-qa runs both.

## The thin-AI smell test (a draft FAILS if any are true)
- Could this paragraph appear on 50 other gardening blogs unchanged? → too generic; add specificity.
- Are claims vague ("water regularly," "choose a good pot") with no numbers, varieties, or thresholds?
- Is it padded with filler intros, "in today's world," restated headings, or obvious definitions?
- Does it list products with no **original selection criteria** (why THIS, who it's for, trade-offs)?
- Does it promise something the title implies but never deliver (intent not satisfied)?

## How we earn authority WITHOUT faked anecdotes (voice is second-person)
Because the voice is "you," authority comes from **demonstrated expertise**, not "I" stories:
- **Specificity:** exact varieties ('Tiny Tim' tomato, not "a tomato"), pot sizes in inches/litres,
  spacing, sun hours, days-to-harvest, temperature ranges.
- **Original selection criteria** for any product/plant list: state the criteria first, then the picks.
- **Trade-offs & honesty:** name downsides, "skip this if…", common mistakes. Generic content never does.
- **Decision helpers:** comparison tables, "best for X" framing, quick-pick summaries.
- **Optional first-person depth:** insert `[PERSONAL TIP: ...]` callout placeholders the user can fill with
  real lived experience. **Never write a fabricated personal experience to fill them.**

## Factual accuracy & safety (YMYL-adjacent — do not guess)
- **Plant toxicity / pet safety / edibility = verify or hedge.** "Is X safe for cats?" must be correct.
  When unsure: state uncertainty and recommend checking ASPCA / extension service. Never assert a guess.
- Cite reputable sources (university extension services, RHS, ASPCA) for safety/horticulture claims.
- Climate/zone advice must note that conditions vary; avoid absolute guarantees ("this WILL grow anywhere").
- No fabricated statistics, study citations, or expert quotes.

## Structure & readability (full spec in `guidelines/content-structure.md`)
- Satisfy the search intent in the first screen; scannable H2/H3; short paragraphs; lists/tables where they help.
- Every post: useful intro (no filler), clear sections, a quick-answer or summary, internal links, optional FAQ.

## editor-qa enforcement checklist
- [ ] Passes the thin-AI smell test (specific, not generic)
- [ ] Stated selection criteria for any product/plant list
- [ ] All safety/toxicity/edibility claims verified or hedged + sourced
- [ ] No fabricated experience, stats, quotes, or studies
- [ ] Intent fully satisfied; title promise delivered
- [ ] `[PERSONAL TIP]` / `[YOUR PHOTO]` placeholders left for the user, not auto-filled
