---
description: Discover, score, and validate candidate niches, then recommend one to commit to.
argument-hint: "[optional: focus area or candidate niches]"
---

Run the niche discovery + validation workflow.

Context: `$ARGUMENTS` (if empty, use the user's interests from `.claude/memory.md` and the leading
candidate, small-space/container gardening).

Steps:
1. Dispatch the **niche-strategist** agent. Pass it `$ARGUMENTS` plus the instruction to evaluate the
   leading candidate against 2–3 sibling sub-niches.
2. The agent writes scorecards to `niche research/` and a comparison file, and returns a recommendation.
3. Present the ranked comparison table + recommended niche + its 4 content pillars + the
   "narrow entry → broad vision" path. Note any numbers labeled `(est — needs validation)` and which
   tool exports would confirm them.
4. Ask the user to confirm the niche. On confirmation, update `.claude/CLAUDE.md` "Current state" and
   `.claude/memory.md`, then recommend `/keyword-cluster <first pillar>`.

Do not write any blog content here — this is strategy only.
