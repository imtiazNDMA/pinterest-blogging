# Design Spec: Content-Craft Guardrails (copywriting, humanization, formatting, anti-slop)

**Date:** 2026-06-25
**Status:** Approved (design) — pending spec review before implementation
**Scope:** Add/expand studio rules that improve readability, humanization, and conversion, plus a
re-examination of the anti-AI-slop guardrail. Studio = `.claude/` content-production system.

---

## 1. Goal

Raise the floor on every post the studio produces so drafts read like a knowledgeable human, scan
cleanly on mobile, and convert — without fabricating experience. Make the rules enforceable: objective
ones are hard gates editor-qa FAILs; subjective ones are flags editor-qa surfaces.

## 2. Decisions (locked)

- **Structure:** Hybrid — two NEW guideline files + EXPAND two existing files + WIRE the two agents.
- **Enforcement:** Tiered — mechanical/objective rules = hard FAIL gates; subjective humanization = guidance flags.
- **Targets:** Concrete numbers (not principles-only) so editor-qa can check objectively.
- **Humanization depth:** Rhythm + reader-connection only. NO fabricated first-person; real experience
  stays in owner-filled `[PERSONAL TIP]`.
- **Location:** New files go in `guidelines/` (not `guardrails/`); their non-negotiable rules carry an
  explicit `(hard gate)` tag, exactly how `content-structure.md` already mixes spec + enforced rules.
- **Emojis:** ZERO emojis anywhere in post content (body, headings, callouts, tables) AND in pin copy
  (overlay text, pin titles, pin descriptions) — absolute hard gate. Deliberate brand choice.

## 3. File plan

| Action | File | Purpose |
|---|---|---|
| NEW | `.claude/guidelines/formatting-and-readability.md` | Scannability spec + measurable targets; hard rules tagged `(hard gate)` |
| NEW | `.claude/guidelines/humanization.md` | Rhythm + reader-connection craft (guidance) |
| EXPAND | `.claude/guardrails/anti-ai-slop.md` | Arrows (hard gate) + re-examination: new phrasing & structural tells; emoji ban |
| EXPAND | `.claude/guidelines/conversion-copywriting.md` | Honest persuasion frameworks + deeper copy levers |
| EXPAND | `.claude/guidelines/pin-spec.md` | Add zero-emoji rule to pin overlay/title/description copy |
| WIRE | `.claude/agents/content-writer.md` | Add the two new files to "Read first"; add craft requirements |
| WIRE | `.claude/agents/editor-qa.md` | Add the two new files to "Read first"; add tiered checklist items |
| WIRE | `.claude/agents/pinterest-strategist.md` | Enforce zero emojis in generated pin copy |

No other files change. `content-quality.md` and `brand-voice.md` get a one-line cross-reference only if
needed to avoid duplication (they already gesture at structure/voice).

---

## 4. Contents

### 4.1 `guidelines/formatting-and-readability.md` (NEW)

Purpose line: how a post is shaped on the page so a mobile pinner can scan it in seconds.

**Measurable targets:**
- **Paragraphs:** 1–3 sentences; mix in 1-line paragraphs. `(hard gate)` none over **4 sentences or ~60 words** ("wall of text").
- **Sentences:** average ≤20 words; `(hard gate)` split any single sentence **>35 words**. Vary length on purpose.
- **Subheads:** an H2/H3 every ~250–350 words. `(hard gate)` no run of body text **>350 words** without a subhead.
- **Bold:** for genuine key takeaways only. `(hard gate)` **≤1 bolded phrase per paragraph**; no bold-spam, no bold-lead on every paragraph.
- **Lists:** use only for 3+ parallel items; keep items grammatically parallel; ≤~7 before grouping. Don't fake-list prose.
- **Reading level:** target Flesch Reading Ease **60–70** (~8th grade). *Guidance* — editor-qa flags if it reads markedly harder (no exact tool available).
- **Emojis:** `(hard gate)` **zero emojis** anywhere in post content.
- **Scannability/mobile:** front-load value in the first line of each section; vary sentence openers; use white space; avoid oversized tables (split or simplify).
- **Headings:** sentence case (matches existing convention), phrased as the reader's question where natural; no colon-padded "Topic: What You Need to Know" headers.

**editor-qa checklist block** (the file ends with its own PASS/FAIL list mirroring the gates above).

### 4.2 `guidelines/humanization.md` (NEW)

Purpose line: how the prose sounds like a person who has actually grown things, within the no-fabrication rule.

- **Burstiness:** deliberately alternate short, punchy sentences with longer ones; kill the uniform 15–20-word AI cadence.
- **Concrete sensory/physical detail:** "the soil pulls away from the pot edge when it's bone dry" beats "check soil moisture regularly".
- **Take a stance:** make a clear call ("skip terracotta on a hot balcony"); no hedge-mush.
- **Natural connectors + direct "you":** conversational but not performative; avoid the AI fake-warm tells (cross-ref `anti-ai-slop.md` A/C).
- **Specificity as humanity:** varieties, sizes, timings — concreteness reads as lived knowledge (cross-ref `content-quality.md`).
- **No fabricated experience:** real "I" lives only in owner-filled `[PERSONAL TIP]`. Never invent "I tested/grew".
- **Final check:** read aloud — does it sound like a knowledgeable friend or a content mill?
- These are *guidance* flags (editor-qa surfaces them); they do not hard-fail on a judgment call.

### 4.3 `guardrails/anti-ai-slop.md` (EXPAND)

**C1 (punctuation tells) — add arrows:**
- `(hard gate)` Ban arrows in prose: `->`, `→`, `=>`, `»`, and `>` used as an arrow. Rewrite to words
  ("leads to", "then", "becomes", "results in"). (Markdown blockquotes `>` at line start are fine.)

**A (banned phrasings) — add tells found in re-examination:**
- "elevate / transform your space", "say hello to / meet [product]", "effortless", "seamless",
  "supercharge", "unlock", "boasts", "nestled", "dive deeper", "without further ado", "let's get started".

**B (structural tells) — add format tells:**
- Emoji as bullets/decoration (✅ 🌱 👉) — reinforced by the absolute emoji ban.
- Bold-lead on every paragraph (cross-ref formatting bold cap).
- Title-Case-Every-Heading; colon-padded headers.
- Over-signposting: "In this section we'll cover…", "Now that we've covered X, let's look at Y".
- "Pro tip:" / "Quick tip:" / "Remember:" overuse.

**De-slop checklist:** add line items for arrows, emojis, and the new tells.

### 4.4 `guidelines/conversion-copywriting.md` (EXPAND)

- **Honest persuasion frameworks:** PAS (problem → agitate → solve) and BAB (before → after → bridge)
  for intros and pick write-ups — used truthfully, never manufacturing fake pain.
- **Feature → benefit translation:** "thick walls *so that* it survives frost on an exposed balcony."
- **One reader, one decision:** reduce choice overload; each pick aimed at one clear situation (ties to the
  distinct "Best for…" rule already added in Fix #3).
- **CTA craft (deeper):** one primary CTA per pick, descriptive anchor, low-pressure; risk-reversal and
  honesty as conversion levers (build on existing section, no duplication).

### 4.6 `guidelines/pin-spec.md` (EXPAND)

- Add to "Copy per pin": `(hard gate)` **zero emojis** in pin overlay text, titles, and descriptions —
  same absolute rule as post content. A keyword + a soft CTA carry the pin; no emoji decoration.

### 4.5 Agent wiring

**`content-writer.md`:**
- Add to "Read first": `guidelines/formatting-and-readability.md`, `guidelines/humanization.md`.
- Add a craft requirement: write to the formatting targets, apply humanization, zero emojis, no arrows.

**`editor-qa.md`:**
- Add the two new files to "Read first".
- Add a **Formatting & readability** gate block (hard): paragraph/sentence caps, subhead spacing,
  bold cap, zero emojis, no arrows.
- Add a **Humanization** guidance block (flags): burstiness, stance, sensory detail, read-aloud.

**`pinterest-strategist.md`:**
- Add a rule that generated pin copy (overlay text, titles, descriptions) contains zero emojis.

---

## 5. Enforcement tiers (summary)

**Hard gates (editor-qa FAIL):**
- No arrows (`->`, `→`, `=>`, `»`, `>`-as-arrow) in prose
- Zero emojis anywhere in post content AND pin copy (overlay/title/description)
- Paragraph ≤4 sentences / ≤~60 words
- Sentence ≤35 words
- No body run >350 words without a subhead
- ≤1 bolded phrase per paragraph
- New banned phrasings from §4.3

**Guidance flags (editor-qa notes, no auto-fail):**
- Flesch reading ease 60–70
- Burstiness / sentence-length variation
- Clear stance, concrete sensory detail
- Persuasion-framework presence on buyer posts

## 6. Out of scope (YAGNI)

- No automated Flesch-score tooling (manual judgment + flag only).
- No changes to pin copy rules (`pin-spec.md`) other than the zero-emoji rule (in scope per §4.6).
- No new slash command; this rides the existing `/new-post` pipeline.
- No rewrite of existing posts here (the sample was already cleaned in commit `e239c0c`).

## 7. Success criteria

- A new draft run through `/new-post` measurably hits the formatting targets and contains no arrows/emojis.
- editor-qa FAILs a planted violation (e.g. an arrow, a 70-word paragraph, an emoji) and PASSes a clean draft.
- The new rules don't contradict existing guardrails; cross-references resolve.
