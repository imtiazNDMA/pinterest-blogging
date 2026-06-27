# Guideline: Formatting & Readability

How a post is shaped on the page so a mobile pinner can scan it in seconds. Used by content-writer;
enforced by editor-qa. Rules tagged `(hard gate)` FAIL the draft; the rest is craft guidance.

## Measurable targets
- **Paragraphs:** default **1–2 sentences**; one-line paragraphs are the house rhythm, not the exception.
  `(hard gate)` none over **2 sentences or ~45 words**. A 3-sentence paragraph is allowed only *sparingly*
  for a genuinely linked point (editor-qa flags it if more than ~1 in 5 paragraphs runs to 3). This is the
  "attention-span" standard: a mobile pinner reads in glances, so give them short blocks with air between.
- **Sentences:** average ≤18 words. `(hard gate)` split any single sentence over **30 words**. Vary length on
  purpose (see `humanization.md`) — a three-word sentence after a long one is the point, not a mistake.
- **Subheads:** an H2/H3 roughly every 250–350 words. `(hard gate)` no run of body text over **350 words** without a subhead.
- **Bold:** for a genuine key takeaway only. `(hard gate)` **≤1 bolded phrase per paragraph**; no bold-spam, no bold-lead on every paragraph.
- **Lists:** use only for 3+ parallel items; keep items grammatically parallel; group if over ~7. Never fake-list prose that should be sentences.
- **Reading level:** target Flesch Reading Ease **60–70** (~8th grade). *Guidance* — editor-qa flags prose that reads markedly harder; not a hard fail.
- **Emojis:** `(hard gate)` **zero emojis** anywhere in the post (body, headings, callouts, tables).

## Narrative flow (keep them glued)
Short blocks scan, but flow is what keeps a reader moving down the page. Storytelling here means **pull**, not
invented anecdotes (the no-fabrication rule still holds — real first-person experience lives only in
`[PERSONAL TIP]`).
- **Hook each section opener** with a recognizable moment the reader feels: "You step onto the balcony, and
  there's nowhere to actually sit." A concrete scene beats a flat topic sentence.
- **Carry momentum across the seam.** End a section pointing forward, so the next heading answers a question the
  reader is already asking. No mechanical "Now let's look at…" signposting (that's an anti-slop tell).
- **One through-line.** The post should read as a single guided walk from problem to styled space, not a pile of
  disconnected tips.
- **Burstiness is the engine.** A three-word sentence after a longer one lands. Uniform short fragments do not
  (see `anti-ai-slop.md` robotic-staccato tell).
- **General second-person mini-scenes are allowed** ("Picture the corner at dusk…"); a *claimed* personal
  experience is not — that stays in `[PERSONAL TIP]`.

## Scannability & mobile-first
- Front-load the value in the first line of every section; the reader decides to keep scrolling there.
- Vary sentence openers — don't start three sentences or paragraphs the same way.
- Use white space; let short paragraphs breathe.
- Keep tables small (split or simplify a table wider than ~4 columns); they get unreadable on a phone.

## Headings
- Sentence case (matches `naming-conventions.md` / house style), phrased as the reader's question where natural.
- No colon-padded headers ("Watering: What You Need to Know") — see `anti-ai-slop.md` structural tells.
- Reader-facing, never scaffold labels (see `content-structure.md`).

## editor-qa formatting checklist
- [ ] No paragraph over 2 sentences / ~45 words (occasional 3-sentence para OK; flag if >~1 in 5)
- [ ] No sentence over 30 words
- [ ] No body run over 350 words without a subhead
- [ ] ≤1 bolded phrase per paragraph; no bold-spam
- [ ] Zero emojis anywhere
- [ ] Lists used only for parallel 3+ items; tables phone-friendly
- [ ] (Flag) Narrative flow: section openers hook, momentum carries across seams, one through-line
- [ ] (Flag) Reading ease ~60–70; sentence openers and lengths vary (burstiness, not staccato)
