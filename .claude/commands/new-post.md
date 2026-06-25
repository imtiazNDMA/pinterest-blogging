---
description: Produce a publish-ready post — draft, QA, monetize, save, and log it.
argument-hint: "<post slug, keyword, or brief>"
---

Produce a publish-ready post for: **$ARGUMENTS**

Pipeline (orchestrate the agents in order; pass each step's output to the next):
1. **Brief:** If a brief exists in the relevant `keyword Research/` cluster file, load it. Otherwise
   dispatch **keyword-researcher** to produce a single-post brief for `$ARGUMENTS`.
2. **Draft:** Dispatch **content-writer** with the brief → writes `Content/<slug>.md` (frontmatter + body,
   brand voice, structure, SEO, `[PERSONAL TIP]`/`[YOUR PHOTO]` placeholders).
3. **Monetize (if buyer intent or products fit):** Dispatch **monetization-strategist** to produce a
   compliant "selection criteria + picks" block (no prices) and confirm affiliate placement + disclosure.
   Insert it into the draft.
4. **QA:** Dispatch **editor-qa** to audit against all guardrails, apply safe fixes, and set
   `status: ready` only if every gate passes. If NEEDS WORK, report what the user must resolve.
5. **Log:** Update the tracker `Content` row → status `Draft`/`Ready`, word count, disclosure/internal/affiliate flags.
6. Report: file path, word count, READY/NEEDS-WORK verdict, the `[PERSONAL TIP]`/`[YOUR PHOTO]` slots the
   user must fill, and recommend `/make-pins <slug>`.

Never fabricate experience, prices, or safety facts. Disclosure goes above the first affiliate link.
