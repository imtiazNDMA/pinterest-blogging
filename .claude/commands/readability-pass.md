---
description: Re-flow a post to the attention-span density standard (1-2 sentence paragraphs, short varied sentences, smooth flow) without touching SEO, links, or compliance.
argument-hint: "<post slug>"
---

Run a readability pass on the post: **$ARGUMENTS**

Follow `playbooks/readability-pass.md` exactly. This is prose surgery — tighten the writing, preserve everything else.

Steps:
1. Load `Content/$ARGUMENTS.md`. Record its word count, keyword set, internal-link count + anchors, disclosure
   placement, and `[PERSONAL TIP]`/`[YOUR PHOTO]` counts — these are the INVARIANTS you must preserve.
2. Re-flow the body to the `formatting-and-readability.md` density standard: paragraphs ≤2 sentences / ~45 words
   (one-line paragraphs as the default rhythm), sentences ≤30 words with deliberate length variation (burstiness,
   not staccato), and the Narrative-flow rules (hook each section opener, carry momentum, one through-line).
3. Do NOT change: frontmatter, keywords, headings, internal links/anchors, affiliate disclosure + placement,
   `{{AMAZON_TAG}}#affiliate` placeholders, any factual/ASPCA safety claim, or the placeholders. Word count stays
   within ~±15%. Introduce no em-dashes, arrows, emojis, false-contrast, or new affiliate links.
4. Edit the file in place; keep `status: ready` unless an invariant couldn't be preserved (then `status: draft`
   and say why).
5. Report: paragraphs split, before→after word count (confirm ±15%), and an explicit INVARIANTS-held line
   (keywords ✓ / internal links N→N ✓ / disclosure ✓ / placeholders N→N ✓ / safety claims ✓).

Note: the tracker doesn't need a status change for a readability re-flow; if you want, bump `Last-Updated` to today
on the post's Content row (CSV-safe: preserve all rows, quote comma fields, verify 51 fields/row).
