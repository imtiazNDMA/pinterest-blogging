# Playbook: Keyword Research

Used by **keyword-researcher** / `/keyword-cluster`. Free-tool, Pinterest-first method.

## The loop
1. **Pinterest first** (it's the traffic source): use the search bar autocomplete — type the seed, record
   the suggested completions (these are real Pinterest searches). Note Trends if the user supplies exports.
2. **Google second** (durable SEO): Google autocomplete, "People Also Ask", "related searches", and the
   "searches related to" block. Capture long-tail phrasings and sub-questions.
3. **Classify** each phrase: intent (informational/buyer), and likely Pinterest demand (visual? idea-driven?).
4. **Estimate** difficulty by inspecting the SERP (giant sites vs small blogs/forums = harder vs easier) and
   volume roughly. **Label every number `(est — needs validation)`.**
5. **Validate (optional but recommended):** user pastes Google Keyword Planner (free w/ Ads account) and/or
   Pinterest Trends exports; replace estimates with real figures and drop the `(est)` label.
6. **Group** into clusters (pillar + supporting) per `guidelines/cluster-schema.md`.
7. **Prioritize** P1/P2/P3 = demand × rankability × monetization fit.

## Outputs
- `keyword Research/<cluster-slug>.md` — cluster map (full schema) + briefs for P1/P2 posts.
- Tracker `Content` rows at status `Idea`.

## Guardrails
- One primary keyword per planned post; avoid cannibalization (two posts targeting the same intent).
- Never present estimates as confirmed data. Be explicit about what's reasoned vs measured.
