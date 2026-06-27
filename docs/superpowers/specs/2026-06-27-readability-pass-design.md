# Readability Pass — Design Spec

**Date:** 2026-06-27
**Status:** approved (brainstorming) → implementing
**Owner request:** "Average attention span has dropped. Run a copywriter pass on all written posts: 1–2 line
paragraphs, shorter sentences, smooth steady flow, strong storytelling to keep readers glued." Plus: update the
house standard so future posts inherit it, and build a re-runnable mechanism.

## Decisions (locked with the owner)
1. **Density:** mostly 1–2 sentences per paragraph, an occasional 3-sentence paragraph allowed *sparingly* for
   rhythm. New hard gate: **≤2 sentences AND ~45 words per paragraph**.
2. **Mechanism:** update the house standard + build a reusable `/readability-pass` command AND re-flow all 14
   posts now. Future posts inherit via `content-writer` + `editor-qa`.
3. **Rollout:** batch all 14 posts in one pass, owner reviews the full set after.

## The new density standard (`guidelines/formatting-and-readability.md`)
| Rule | Old | New |
|---|---|---|
| Paragraph | ≤4 sentences / ~60 words (hard gate) | **≤2 sentences / ~45 words (hard gate)**; a 3-sentence para only sparingly (flag if frequent) |
| Sentence | split >35 words | **split >30 words**; target avg ≤18 |
| One-line paragraphs | "mix in" | **default rhythm — encouraged** |
| Subheads / ≤1 bold / zero emoji / lists | — | unchanged |

## Narrative-flow layer (storytelling within no-fabrication)
Storytelling = **pull**, not invented anecdotes. The guideline adds a "Narrative flow" section requiring:
- Section openers that hook with a recognizable scenario ("You step out, and there's nowhere to sit").
- Transitions that carry momentum into the next section; a through-line top to bottom.
- **Burstiness:** a short punchy sentence after a longer one (this also satisfies anti-slop).
- General second-person mini-scenes allowed. Claimed personal experience stays ONLY in `[PERSONAL TIP]`.

## Anti-slop reconciliation (key risk)
Uniform staccato (many identical short fragments) is itself an AI tell. `anti-ai-slop.md` gains a new structural
tell — **"robotic staccato / uniform short-sentence cadence"** — and the new density rule is explicitly paired
with "vary length on purpose." Short ≠ choppy.

## Invariants the pass MUST NOT change (re-flow reshapes prose only)
Frontmatter; title; primary + secondary keywords; every internal link + anchor; affiliate disclosure + its
placement; `{{AMAZON_TAG}}#affiliate` placeholders; all `[PERSONAL TIP]` / `[YOUR PHOTO]` markers; every
factual/ASPCA safety claim; `status: ready`. Word count stays within ~±15%. Zero new fabrication. No prices.

## Files changed
- `guidelines/formatting-and-readability.md` — new gate numbers + Narrative-flow section.
- `guardrails/anti-ai-slop.md` — add robotic-staccato tell (B) + de-slop checklist line.
- `agents/editor-qa.md` — density gate numbers (≤2 sentences / ~45 words; sentence >30).
- `agents/content-writer.md` — write to new density + narrative flow.
- `playbooks/readability-pass.md` — NEW, the procedure.
- `commands/readability-pass.md` — NEW, `/readability-pass <slug>`.

## Batch execution
Re-flow 14 `Content/*.md` posts in parallel (independent files), each following the readability-pass playbook,
then a verify gate confirms invariants held + new density met. List of posts in the playbook.

## Follow-up (queued, separate task)
After this pass: build a complete pillar-coverage post list in `todos.md` (gap analysis per pillar — written vs
needed) so pillars can be completed one by one.
