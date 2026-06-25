# Studio Fixes — TODO

> **Purpose:** Track the studio fixes identified during the 2026-06-24 `/new-post` stress test
> (sample post `Content/best-self-watering-planters-balcony.md`, tracker Record ID 4).
>
> **Rule:** Update this file after EACH fix is applied — check the box, add the date and a one-line
> note on what changed. A fix isn't done until its box is checked here.

---

## Pending fixes

- [x] **1. (High) Scaffolding headings leak into posts** — _done 2026-06-25_
  Literal scaffold H2s (`## Intro`, `## Quick answer`, `## Wrap-up`, `## Comparison table`) got
  published as real headings.
  **Fix:** `guidelines/content-structure.md` + `templates/post-skeleton.md` — intro = no heading;
  make the others reader-facing. Add an `editor-qa` check that flags scaffold-leak headings.

- [x] **2. (Med) Too few `[YOUR PHOTO]` markers** — _done 2026-06-25_
  `content-writer` left only 1 photo marker; pin creation needs 2–4 (one per pin angle).
  **Fix:** Require `content-writer` to leave 2–4 `[YOUR PHOTO]` markers, one per pin angle.

- [x] **3. (Med) "Best for…" segments not distinct** — _done 2026-06-25_
  Sample had 2 picks both = floor grow box.
  **Fix:** `guidelines/conversion-copywriting.md` — require "Best for…" segments to be DISTINCT
  product categories.

- [x] **4. (Low) No year-in-title policy** — _done 2026-06-25_
  Sample used "2026 Picks" → maintenance debt.
  **Fix:** `guidelines/headlines-and-titles.md` — add a year-in-title policy.

- [x] **5. (Med) Tracker logging is orchestration-only** — _done 2026-06-25_
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

- **2026-06-25 — Fix #1 (scaffold-heading leak):** Moved writer cues into HTML comments in
  `templates/post-skeleton.md` (intro now has no heading; TL;DR + closing headings are reader-facing
  placeholders). Updated `guidelines/content-structure.md` skeleton items 1/2/6 + buyer item 5 and
  added a "Headings are reader-facing" rule. Added a grep gate to `agents/editor-qa.md` that FAILs any
  bare scaffold-label heading (Intro / Quick answer / TL;DR / Wrap-up / Comparison table / Conclusion).
- **2026-06-25 — Fix #2 (photo markers):** `agents/content-writer.md` now requires 2–4 `[YOUR PHOTO]`
  markers (one per pin angle) + reports the count in its self-check. `guidelines/content-structure.md`
  states the 2–4 count. `agents/editor-qa.md` grep-counts `[YOUR PHOTO` and FAILs if <2.
  `templates/post-skeleton.md` carries a "2–4, one per pin angle" cue.
- **2026-06-25 — Fix #3 (distinct "Best for…" picks):** `guidelines/conversion-copywriting.md` framing
  rule 3 + QA check now require each "Best for…" segment to be a DISTINCT product (different
  category/form factor); two relabeled identicals = FAIL. Mirrored in `agents/editor-qa.md` craft check
  and `agents/content-writer.md` buyer-post craft line.
- **2026-06-25 — Fix #4 (year-in-title policy):** `guidelines/headlines-and-titles.md` gained a
  "Year-in-title policy" section + an Avoid bullet (default: no year in SEO title/H1/slug; only if a
  committed annual refresh; pins may use it sparingly). `agents/editor-qa.md` flags/strips stray years.
- **2026-06-25 — Fix #5 (explicit tracker logging):** `commands/new-post.md` step 5 now spells out the
  exact `Content`-row columns to find/create + set (status, word count, dates, disclosure/internal/
  affiliate flags, URL, next action) and to confirm the Record ID in the report. Added a "Tracker
  logging (fallback)" section to `agents/content-writer.md` + `agents/editor-qa.md` (log the row when
  dispatched directly, else emit a loud `⚠ TRACKER NOT LOGGED` line). `guidelines/tracker-schema.md`
  "Who writes what" gained the matching fallback note.
