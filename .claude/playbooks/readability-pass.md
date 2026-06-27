# Playbook: Readability Pass

A focused re-flow that tightens an existing, already-QA'd post to the **attention-span density standard**
without changing its facts, SEO, links, or compliance. This is prose surgery, not a rewrite.

Run when: re-flowing the back catalog to the tighter standard, or polishing any post that reads dense.
Invoked by `/readability-pass <slug>`; the new density is also baked into `content-writer` for fresh posts.

References: `guidelines/formatting-and-readability.md` (density gate + Narrative flow), `guardrails/anti-ai-slop.md`
(robotic-staccato tell), `guidelines/humanization.md`.

## The target (from formatting-and-readability.md)
- **Paragraphs:** default 1–2 sentences; one-line paragraphs are the house rhythm. Hard gate: none over
  **2 sentences / ~45 words**. A 3-sentence paragraph only sparingly (≤~1 in 5).
- **Sentences:** split anything over **30 words**; average ≤18. **Vary length on purpose** (burstiness) — a
  short sentence after a long one. Never a run of identical short fragments (that's the staccato tell).
- **Flow:** hook each section opener with a recognizable moment; carry momentum across the seam into the next
  heading; keep one through-line problem→styled-space. Storytelling = pull, NOT invented anecdotes.

## INVARIANTS — do NOT change (re-flow reshapes prose only)
- Frontmatter (title, slug, keywords, meta, internal_links list, status, monetized flags) — untouched.
- Every **primary + secondary keyword** still present (title, first 100 words, ≥1 H2).
- Every **internal link + its anchor text** — same targets, same count.
- **Affiliate disclosure** wording and its placement ABOVE the first affiliate link.
- `{{AMAZON_TAG}}#affiliate` placeholders — never swap for real links; never add new affiliate links.
- All `[PERSONAL TIP]` and `[YOUR PHOTO]` markers — same count, same positions, never filled.
- Every factual / horticulture / ASPCA pet-safety claim — verbatim meaning; do not soften or strengthen a
  safety claim. No prices, no "cheapest", no stock language introduced.
- **Word count within ~±15%** of the original (you are reshaping, not cutting content or padding).
- Headings stay reader-facing and keyword-aligned; do not rename them.

## Pass order
1. **Read the whole post once.** Note the through-line and where it reads dense or choppy.
2. **Split the walls.** Break every paragraph over 2 sentences / ~45 words into short blocks. Add air.
3. **Shorten + vary sentences.** Split anything over 30 words. Then re-check for staccato — restore a longer
   flowing sentence where three short ones in a row read machine-chopped. Burstiness, not uniformity.
4. **Flow pass.** Strengthen each section opener into a hook; smooth the transition into the next heading; make
   sure it reads as one guided walk. No "Now let's look at…" signposting.
5. **Invariant check.** Re-verify the INVARIANTS list above, line by line. This is the gate that protects SEO
   and compliance from a readability edit.
6. **Anti-slop re-scan.** Confirm no new em-dashes, arrows, emojis, false-contrast, or staccato were introduced.

## Output
- Edit `Content/<slug>.md` in place; keep `status: ready` (a readability re-flow doesn't downgrade a passed post,
  but if step 5 finds an invariant you couldn't preserve, set `status: draft` and report it).
- Report: paragraphs split, before/after word count (confirm ±15%), and an explicit INVARIANTS-held confirmation
  (keywords ✓, internal links N→N ✓, disclosure placement ✓, placeholders N→N ✓, safety claims ✓).

## The one rule that matters most
A readability pass that changes a keyword, drops an internal link, moves the disclosure, or alters a safety
claim has failed — even if the prose got better. Prose surgery preserves the patient.
