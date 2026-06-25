---
description: Run the optimization loop — ingest metrics, find winners/losers, output prioritized actions.
argument-hint: "[paste metric exports, or leave empty to review tracker state]"
---

Run the weekly/monthly optimization review.

1. If the user pasted exports (GA4 / Search Console / Pinterest / Amazon / ad RPM) in `$ARGUMENTS` or the
   chat, use them. Otherwise review current tracker state and tell the user exactly which exports to paste
   for a fuller review. **Never invent metrics.**
2. Dispatch the **analytics-optimizer** agent to: update tracker metric columns + Net Profit/CTR/RPM,
   identify winners (expand), close-but-missing (rewrite titles/redesign pins), dead weight (retire/redesign),
   content gaps (new posts), and internal-linking debt.
3. Present a **prioritized next-actions list** (P1→P3), each mapped to the exact command to run
   (`/keyword-cluster`, `/new-post`, `/make-pins`, redesign pin PB-###, refresh slug).
4. Show a 5-line scorecard vs the current milestone/KPIs from `.claude/memory.md`. Lead with the top 3 moves.
