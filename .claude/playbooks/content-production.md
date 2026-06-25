# Playbook: Content Production

Used by `/new-post` (keyword-researcher → content-writer → monetization-strategist → editor-qa). Goal:
publish-ready drafts that satisfy intent, stay compliant, and feed Pinterest.

## Steps
1. **Brief** — load from the cluster file or generate one (keyword, intent, sub-questions, products, internal links, pin angles).
2. **Draft** — content-writer writes `Content/<slug>.md` to the correct skeleton (informational vs buyer),
   in second-person voice, specific and honest, with `[PERSONAL TIP]`/`[YOUR PHOTO]` placeholders.
3. **Monetize** — if products fit, monetization-strategist inserts a compliant "selection criteria + picks"
   block (no prices) and confirms disclosure placement.
4. **QA + de-slop** — editor-qa runs the `editing-and-deslop.md` passes (anti-slop kill pass → specificity →
   hook/title → conversion → SEO/links → read-aloud), applies safe fixes, sets `status: ready` only on full pass.
5. **Log** — update the tracker `Content` row (status, word count, disclosure/internal/affiliate flags).
6. **Handoff** — recommend `/make-pins <slug>`; flag the `[PERSONAL TIP]`/`[YOUR PHOTO]` slots for the user.

## Per-post requirements (the roadmap's "post requirements")
- A specific search intent; helpful (no-filler) intro; clear scannable headings.
- Original selection criteria / opinions (not generic).
- Internal links to related posts (≥3).
- Affiliate disclosure before affiliate links; products only where natural.
- Notes for 3–8 Pinterest-ready images / pin graphics (the `[YOUR PHOTO]` spots seed these).

## Cadence
- 3–5 quality posts/week (user writes/edits; studio drafts). Quality gate over quantity — a draft that
  fails editor-qa does not ship. Update older posts periodically (freshness helps rankings).

## The big risk (read this)
"Full drafts, minimal editing" only works because editor-qa + content-quality guardrail enforce specificity
and accuracy. If drafts start feeling generic, tighten the briefs and add more `[PERSONAL TIP]` depth — thin
AI content is the #1 way this whole model fails.
