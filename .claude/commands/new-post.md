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
5. **Log (do this explicitly — a post not in the CSV doesn't exist):** Update `pinterest_blog_master_tracker.csv`
   per `guidelines/tracker-schema.md`.
   - **Find or create the `Content` row:** match the existing `Idea` row (by Post Title / Primary Keyword) that
     keyword-researcher created; if none exists, **append a new `Content` row** with a fresh `Record ID`.
   - **Set/update these columns:** `Content Status` = `Ready` if editor-qa passed else `Draft`; `Word Count`;
     `Draft Start` (today, ISO, if newly drafted); `Last-Updated` (today, ISO); `Affiliate Links Added` (Y/N);
     `Amazon Products Featured`; `Disclosure Added` (Y/N); `Internal Links Added` (count); `Post URL` (if known);
     `Next Action` (e.g. "fill PERSONAL TIP + photos, then /make-pins").
   - Dates ISO `YYYY-MM-DD`. **Numbers only from real data** — leave metric columns blank.
   - After writing, **confirm in the report** which Record ID you created/updated.
6. Report: file path, word count, READY/NEEDS-WORK verdict, the `[PERSONAL TIP]`/`[YOUR PHOTO]` slots the
   user must fill, and recommend `/make-pins <slug>`.

Never fabricate experience, prices, or safety facts. Disclosure goes above the first affiliate link.
