# Studio Fixes — TODO

> **Purpose:** Track the studio fixes identified during the 2026-06-24 `/new-post` stress test
> (sample post `Content/best-self-watering-planters-balcony.md`, tracker Record ID 4).
>
> **Rule:** Update this file after EACH fix is applied — check the box, add the date and a one-line
> note on what changed. A fix isn't done until its box is checked here.

---

## Pending fixes

- [ ] **1. (High) Scaffolding headings leak into posts**
  Literal scaffold H2s (`## Intro`, `## Quick answer`, `## Wrap-up`, `## Comparison table`) got
  published as real headings.
  **Fix:** `guidelines/content-structure.md` + `templates/post-skeleton.md` — intro = no heading;
  make the others reader-facing. Add an `editor-qa` check that flags scaffold-leak headings.

- [ ] **2. (Med) Too few `[YOUR PHOTO]` markers**
  `content-writer` left only 1 photo marker; pin creation needs 2–4 (one per pin angle).
  **Fix:** Require `content-writer` to leave 2–4 `[YOUR PHOTO]` markers, one per pin angle.

- [ ] **3. (Med) "Best for…" segments not distinct**
  Sample had 2 picks both = floor grow box.
  **Fix:** `guidelines/conversion-copywriting.md` — require "Best for…" segments to be DISTINCT
  product categories.

- [ ] **4. (Low) No year-in-title policy**
  Sample used "2026 Picks" → maintenance debt.
  **Fix:** `guidelines/headlines-and-titles.md` — add a year-in-title policy.

- [ ] **5. (Med) Tracker logging is orchestration-only**
  Agents don't log to the tracker; only the command does.
  **Fix:** Make `/new-post` logging explicit + add an agent fallback note.

- [ ] **6. (Low) Ambiguous H2 keyword rule**
  **Fix:** `guardrails/seo-rules.md` — clarify "primary keyword OR close variant in ≥1 H2."

---

## Related follow-ups (not part of the 6 fixes)

- [ ] Re-run `editor-qa` on `Content/best-self-watering-planters-balcony.md` to clean it under the
  new anti-slop rules (still has 36 em-dashes; cap allows ~6). Capture before/after as proof.
- [ ] Commit the studio to git (repo currently has no commits; detached `HEAD`).

---

## Changelog

_(Add an entry here each time a box above is checked.)_
