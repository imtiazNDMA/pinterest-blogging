---
description: Create a fresh-pin batch (copy + Canva briefs + schedule) for a post.
argument-hint: "<post slug>"
---

Create a Pinterest pin batch for the post: **$ARGUMENTS**

Steps:
1. Load `Content/$ARGUMENTS.md` (its keyword, hooks, `[YOUR PHOTO]` notes).
2. Dispatch the **pinterest-strategist** agent. It produces 4–6 FRESH pins across distinct angles
   (search/curiosity/product/budget/beginner/seasonal/list), each with overlay text, a Canva design brief,
   keyword-rich title, varied description, board assignment, suggested filename, destination `https://bloomandlantern.com/<slug>`,
   and a spaced schedule. Assign a `Pin Batch ID` (PB-###).
3. Save the batch to `Content/pins/$ARGUMENTS-pins.md` (filled `templates/pin-batch.md`).
4. Append `Pin` rows to the tracker (Batch ID, Title, Angle, Board, Status=Draft, scheduled date).
5. Report the batch summary, the Batch ID, and the first suggested publish date. Remind: 2:3 / 1000×1500,
   space them out, design in Canva, schedule with the Pinterest native scheduler.
