# Content-Craft Guardrails Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add copywriting, humanization, and formatting/readability rules to the content studio, re-examine the anti-AI-slop guardrail (arrows + new tells), and ban emojis in all post and pin copy — enforced by editor-qa.

**Architecture:** Two new `guidelines/` files (formatting-and-readability, humanization) plus expansions to `anti-ai-slop.md`, `conversion-copywriting.md`, and `pin-spec.md`. The two drafting/QA agents and the pinterest-strategist are wired to read/enforce them. Objective rules are hard gates editor-qa FAILs; subjective humanization rules are flags it surfaces.

**Tech Stack:** Markdown files in `.claude/`. No build, no test framework — verification is `grep` (Grep tool) for rule presence/consistency and a final planted-violation check.

## Global Constraints

- All studio rule files are Markdown under `.claude/`. Match the existing house style: `# Guardrail:` / `# Guideline:` H1, a one-line purpose, `(hard gate)` inline tag for enforced rules, an editor-qa checklist block at the end.
- Hard-gate numbers (verbatim): paragraph ≤4 sentences / ≤~60 words; sentence ≤35 words; no body run >350 words without a subhead; ≤1 bolded phrase per paragraph.
- Reading level target: Flesch Reading Ease 60–70 — **guidance flag only**, never a hard fail (no scoring tool in pipeline).
- **Zero emojis** anywhere in post content (body, headings, callouts, tables) AND pin copy (overlay/title/description) — absolute hard gate.
- **No arrows** in prose: `->`, `→`, `=>`, `»`, and `>` used as an arrow — hard gate. Markdown blockquote `>` at line start (e.g. `[PERSONAL TIP]` callouts) is EXEMPT.
- Humanization rules are guidance flags, not hard fails.
- Voice stays second-person; real first-person only via owner-filled `[PERSONAL TIP]`. Never fabricate experience.
- Commit after each task. End commit messages with the Co-Authored-By trailer used in this repo.
- Update `todos.md` changelog in the final task.

---

### Task 1: Create `formatting-and-readability.md`

**Files:**
- Create: `.claude/guidelines/formatting-and-readability.md`

**Interfaces:**
- Produces: a guideline file other tasks reference by path; editor-qa (Task 7) and content-writer (Task 6) link to it. Its `(hard gate)` rules are the source of truth for the formatting FAIL checks.

- [ ] **Step 1: Verify the file does not yet exist**

Grep for `formatting-and-readability` across `.claude/` — expected: no file match (only the spec/plan in `docs/`).

- [ ] **Step 2: Write the file** with this exact content:

```markdown
# Guideline: Formatting & Readability

How a post is shaped on the page so a mobile pinner can scan it in seconds. Used by content-writer;
enforced by editor-qa. Rules tagged `(hard gate)` FAIL the draft; the rest is craft guidance.

## Measurable targets
- **Paragraphs:** 1–3 sentences; mix in one-line paragraphs for rhythm. `(hard gate)` none over **4 sentences or ~60 words** (the "wall of text" fail).
- **Sentences:** average ≤20 words. `(hard gate)` split any single sentence over **35 words**. Vary length on purpose (see `humanization.md`).
- **Subheads:** an H2/H3 roughly every 250–350 words. `(hard gate)` no run of body text over **350 words** without a subhead.
- **Bold:** for a genuine key takeaway only. `(hard gate)` **≤1 bolded phrase per paragraph**; no bold-spam, no bold-lead on every paragraph.
- **Lists:** use only for 3+ parallel items; keep items grammatically parallel; group if over ~7. Never fake-list prose that should be sentences.
- **Reading level:** target Flesch Reading Ease **60–70** (~8th grade). *Guidance* — editor-qa flags prose that reads markedly harder; not a hard fail.
- **Emojis:** `(hard gate)` **zero emojis** anywhere in the post (body, headings, callouts, tables).

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
- [ ] No paragraph over 4 sentences / ~60 words
- [ ] No sentence over 35 words
- [ ] No body run over 350 words without a subhead
- [ ] ≤1 bolded phrase per paragraph; no bold-spam
- [ ] Zero emojis anywhere
- [ ] Lists used only for parallel 3+ items; tables phone-friendly
- [ ] (Flag) Reading ease ~60–70; sentence openers vary
```

- [ ] **Step 3: Verify content landed**

Grep for `wall of text` and `≤1 bolded phrase per paragraph` and `zero emojis` in the new file — expected: all present.

- [ ] **Step 4: Commit**

```bash
git add .claude/guidelines/formatting-and-readability.md
git commit -m "feat(studio): add formatting-and-readability guideline

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 2: Create `humanization.md`

**Files:**
- Create: `.claude/guidelines/humanization.md`

**Interfaces:**
- Produces: a guideline file content-writer (Task 6) reads and editor-qa (Task 7) flags against. All rules here are guidance, not hard gates.

- [ ] **Step 1: Verify the file does not yet exist**

Grep for `humanization` across `.claude/` — expected: no file match.

- [ ] **Step 2: Write the file** with this exact content:

```markdown
# Guideline: Humanization

How the prose sounds like a person who has actually grown things — within the studio's no-fabrication
rule. Used by content-writer; editor-qa surfaces these as flags (judgment calls, not hard fails).
Removing AI tells is `anti-ai-slop.md`; this file is about adding human rhythm and connection.

## Rhythm (burstiness)
- Deliberately alternate short, punchy sentences with longer ones. Uniform 15–20-word sentences are the
  flattest AI tell. A three-word sentence after a long one lands.
- Vary paragraph length too (see `formatting-and-readability.md`).

## Connection
- **Concrete sensory/physical detail** beats abstraction: "the soil pulls away from the pot edge when it's
  bone dry" over "check soil moisture regularly".
- **Take a stance.** Make the call: "skip terracotta on a hot balcony." No hedge-mush, no "it depends" without saying on what.
- **Direct "you"** and natural connectors, but avoid the fake-conversational AI tells ("Here's the thing",
  "Let's dive in", rhetorical-question fragments) — see `anti-ai-slop.md` A and C.
- **Specificity reads as lived knowledge:** varieties, sizes, timings, thresholds (cross-ref `content-quality.md`).

## The no-fabrication line
- The post is second person. Real first-person experience lives ONLY in owner-filled `[PERSONAL TIP]` callouts.
- Never invent "I tested / I grew / in my experience". Demonstrated expertise (specifics, trade-offs, a clear
  recommendation) earns authority without faking anecdotes.

## Final check
- Read it aloud. Does it sound like a knowledgeable friend explaining this, or like a content mill? If the
  latter, rewrite the section — don't surface-patch.

## editor-qa humanization flags (surface, don't auto-fail)
- [ ] Sentence and paragraph length vary (not uniform AI cadence)
- [ ] At least some concrete sensory/physical detail, not all abstraction
- [ ] Takes a clear stance where a recommendation is due
- [ ] Passes the read-aloud test; no fabricated first-person
```

- [ ] **Step 3: Verify content landed**

Grep for `burstiness` and `no-fabrication` and `read-aloud` in the new file — expected: all present.

- [ ] **Step 4: Commit**

```bash
git add .claude/guidelines/humanization.md
git commit -m "feat(studio): add humanization guideline

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 3: Expand `anti-ai-slop.md` (arrows + new tells + emoji)

**Files:**
- Modify: `.claude/guardrails/anti-ai-slop.md`

**Interfaces:**
- Consumes: existing sections A (banned phrasings), B (structural tells), C1 (punctuation tells), and the de-slop checklist.
- Produces: arrow ban + emoji ban + expanded tell lists that editor-qa (Task 7) and content-writer (Task 6) rely on.

- [ ] **Step 1: Verify the rules are absent**

Grep `anti-ai-slop.md` for `Arrows` and `emoji` and `nestled` — expected: no matches (none present yet).

- [ ] **Step 2: Add the arrow rule to C1.** After the "Also banned: the emphatic dramatic fragment" line at the end of section C1, insert:

```markdown
- **Arrows are banned in prose `(hard gate)`:** `->`, `→`, `=>`, `»`, and `>` used as an arrow. They are a
  layout/notes tell, not writing. Rewrite to words: "leads to", "then", "becomes", "results in".
  (A Markdown blockquote `>` at the start of a line — e.g. a `[PERSONAL TIP]` callout — is fine.)
```

- [ ] **Step 3: Add new phrasing tells to section A.** After the "Closing slop" line, insert a new line:

```markdown
**Hype/marketing tells:** "elevate", "transform your space", "say hello to", "meet [product]", "effortless",
"seamless", "supercharge", "unlock", "boasts", "nestled", "dive deeper", "without further ado", "let's get started".
```

- [ ] **Step 4: Add new structural/format tells to section B.** After the "Fake personality" bullet, insert:

```markdown
- **Emojis as decoration/bullets** (✅ 🌱 👉): banned outright — see the absolute emoji ban below.
- **Bold-lead on every paragraph** / bold-spam: see `formatting-and-readability.md` bold cap.
- **Title-Case Every Heading** and **colon-padded headers** ("Watering: What You Need to Know"): use sentence case, no colon padding.
- **Over-signposting:** "In this section we'll cover…", "Now that we've covered X, let's look at Y." Just write the section.
- **"Pro tip:" / "Quick tip:" / "Remember:" overuse:** at most rarely, and only with a genuinely non-obvious tip.
```

- [ ] **Step 5: Add the absolute emoji ban.** At the end of section C (after C2), add a new subsection:

```markdown
### C3. Emojis — zero, always `(hard gate)`
No emojis anywhere in post content (body, headings, callouts, tables) or in pin copy. This is a brand choice,
not a style preference. A keyword and a specific hook carry the text; emoji decoration reads as low-effort AI/social filler.
```

- [ ] **Step 6: Add checklist lines.** In "The de-slop test", after the C1 em-dash checkbox, add:

```markdown
- [ ] **No arrows** (`->`, `→`, `=>`, `»`, `>`-as-arrow) in prose (C1)
- [ ] **Zero emojis** anywhere in content or pin copy (C3)
- [ ] No hype/marketing tells, over-signposting, colon/Title-Case headers, or "Pro tip:" overuse (A/B)
```

- [ ] **Step 7: Verify all additions landed**

Grep `anti-ai-slop.md` for `Arrows are banned`, `C3. Emojis`, `nestled`, `Over-signposting` — expected: all present.

- [ ] **Step 8: Commit**

```bash
git add .claude/guardrails/anti-ai-slop.md
git commit -m "feat(studio): anti-slop re-examination — ban arrows + emojis, add tells

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 4: Expand `conversion-copywriting.md`

**Files:**
- Modify: `.claude/guidelines/conversion-copywriting.md`

**Interfaces:**
- Consumes: existing "Recommendation framing" and "CTAs" sections + the distinct "Best for…" rule (Fix #3).
- Produces: persuasion-framework guidance editor-qa (Task 7) flags on buyer posts.

- [ ] **Step 1: Verify absent**

Grep `conversion-copywriting.md` for `Problem-Agitate` and `feature` (benefit translation) — expected: no matches.

- [ ] **Step 2: Add a frameworks section.** After the "Recommendation framing that converts" numbered list, insert:

```markdown
## Honest persuasion frameworks (use truthfully)
- **PAS — Problem → Agitate → Solve:** name the reader's real problem, show its concrete cost, then solve it.
  "Forget to water for three days and a balcony pot in full sun is toast. A self-watering reservoir buys you that slack."
  Never manufacture fake pain — agitate only a problem the reader actually has.
- **BAB — Before → After → Bridge:** the frustrating now, the better after, the product as the bridge. Keep it true.
- **Feature → benefit translation:** every feature gets a "so that you…". "Thick double walls *so that* it
  survives frost on an exposed balcony." A spec the reader can't translate to a benefit doesn't convert.
- **One reader, one decision:** aim each pick at one clear situation; too many near-identical options stall the
  choice (ties to the distinct "Best for…" rule). Reduce, don't pad.
```

- [ ] **Step 3: Verify landed**

Grep `conversion-copywriting.md` for `Problem → Agitate → Solve` and `so that you` — expected: present.

- [ ] **Step 4: Commit**

```bash
git add .claude/guidelines/conversion-copywriting.md
git commit -m "feat(studio): deepen conversion-copywriting (PAS/BAB, benefit translation)

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 5: Add emoji ban to `pin-spec.md` + `pinterest-strategist.md`

**Files:**
- Modify: `.claude/guidelines/pin-spec.md`
- Modify: `.claude/agents/pinterest-strategist.md`

**Interfaces:**
- Produces: pin-copy emoji ban enforced by the pinterest-strategist and (via `/make-pins`) any QA.

- [ ] **Step 1: Verify absent**

Grep both files for `emoji` — expected: no matches.

- [ ] **Step 2: Edit `pin-spec.md`.** In the "Copy per pin" section, after the "Pin description" bullet, add:

```markdown
- **Zero emojis `(hard gate)`** in overlay text, pin titles, and descriptions. A keyword plus a specific
  hook and soft CTA carry the pin; no emoji decoration (matches the post content rule in `anti-ai-slop.md` C3).
```

- [ ] **Step 3: Edit `pinterest-strategist.md`.** Add a hard rule (in its rules/output section) that generated pin copy — overlay text, titles, descriptions — contains zero emojis, per `pin-spec.md` and `anti-ai-slop.md` C3. (Read the file first to place it in the existing rules list; match surrounding style.)

- [ ] **Step 4: Verify landed**

Grep both files for `emoji` — expected: present in each.

- [ ] **Step 5: Commit**

```bash
git add .claude/guidelines/pin-spec.md .claude/agents/pinterest-strategist.md
git commit -m "feat(studio): ban emojis in pin copy

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 6: Wire `content-writer.md`

**Files:**
- Modify: `.claude/agents/content-writer.md`

**Interfaces:**
- Consumes: the new guideline files (Tasks 1–2) and expanded guardrails (Tasks 3–4).
- Produces: a drafting agent that applies all new rules at write time.

- [ ] **Step 1: Verify absent**

Grep `content-writer.md` for `formatting-and-readability` and `humanization` — expected: no matches.

- [ ] **Step 2: Add to "Read first".** After the `content-structure.md` line, add:

```markdown
- `.claude/guidelines/formatting-and-readability.md`, `humanization.md` (readability targets + human rhythm)
```

- [ ] **Step 3: Add a craft requirement.** In "Craft requirements", add a bullet:

```markdown
- **Formatting & humanization:** write to `formatting-and-readability.md` targets (paragraphs ≤4 sentences,
  sentences ≤35 words, a subhead every ~300 words, ≤1 bold/paragraph); apply `humanization.md` (vary sentence
  length, concrete detail, take a stance). **Zero emojis. No arrows** (`->`/`→`); write the words instead.
```

- [ ] **Step 4: Verify landed**

Grep `content-writer.md` for `formatting-and-readability` and `Zero emojis. No arrows` — expected: present.

- [ ] **Step 5: Commit**

```bash
git add .claude/agents/content-writer.md
git commit -m "feat(studio): wire content-writer to new formatting/humanization rules

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 7: Wire `editor-qa.md` (tiered checks)

**Files:**
- Modify: `.claude/agents/editor-qa.md`

**Interfaces:**
- Consumes: every new/expanded rule file.
- Produces: the enforcement layer — hard FAIL gates + guidance flags.

- [ ] **Step 1: Verify absent**

Grep `editor-qa.md` for `formatting-and-readability` and `Formatting & readability` — expected: no matches.

- [ ] **Step 2: Add to "Read first".** Append to the guidelines line:

```markdown
- `.claude/guidelines/formatting-and-readability.md`, `humanization.md`
```

- [ ] **Step 3: Add a hard-gate block.** After the Anti-AI-slop gate block, add:

```markdown
**Formatting & readability (formatting-and-readability.md) — hard gates**
- [ ] **No arrows:** grep the draft for `->`, `→`, `=>`, `»`. Any in prose = FAIL (Markdown blockquote `>` exempt). Rewrite to words.
- [ ] **Zero emojis:** scan body, headings, callouts, tables. Any emoji = FAIL.
- [ ] **No wall-of-text paragraph:** any paragraph over ~4 sentences / ~60 words = FAIL; split it.
- [ ] **No over-long sentence:** any sentence over ~35 words = FAIL; split it.
- [ ] **Subhead spacing:** any body run over ~350 words with no H2/H3 = FAIL; add one.
- [ ] **Bold cap:** more than one bolded phrase in a paragraph, or bold-lead on every paragraph = FAIL.

**Humanization (humanization.md) — guidance flags (note, don't auto-fail on judgment)**
- [ ] Sentence/paragraph length varies; not uniform AI cadence
- [ ] Concrete sensory detail present; takes a clear stance; passes read-aloud
- [ ] (Flag) Reading ease ~60–70
```

- [ ] **Step 4: Verify landed**

Grep `editor-qa.md` for `No arrows:` and `Zero emojis:` and `wall-of-text` and `Humanization (humanization.md)` — expected: all present.

- [ ] **Step 5: Commit**

```bash
git add .claude/agents/editor-qa.md
git commit -m "feat(studio): add editor-qa formatting hard gates + humanization flags

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

### Task 8: End-to-end validation + bookkeeping

**Files:**
- Create (temp): `scratchpad` fixture for the planted-violation check (not committed)
- Modify: `todos.md`

**Interfaces:**
- Consumes: all prior tasks.
- Produces: proof the gates fire, plus updated project bookkeeping.

- [ ] **Step 1: Cross-reference integrity check**

Grep across `.claude/` for `formatting-and-readability` and `humanization` — expected: referenced by content-writer.md and editor-qa.md (not only the files themselves). Confirm no broken references.

- [ ] **Step 2: Planted-violation check (the "test")**

Create a tiny fixture in the session scratchpad containing: one arrow (`->`), one emoji, a 70-word run-on sentence, and a paragraph bolding three phrases. Walk it against the Task 7 hard-gate checklist and confirm each violation maps to a FAIL line. (This validates the checklist is concrete enough to catch real violations. Delete the fixture after.)

- [ ] **Step 3: Confirm the arrow grep does not false-positive on callouts**

Grep `Content/best-self-watering-planters-balcony.md` for `^>` (blockquote) vs `->`/`→` (arrows) — expected: blockquote callouts present, zero arrows. Confirms the exemption is correct and the cleaned sample still passes.

- [ ] **Step 4: Update `todos.md`**

Add a "Content-craft guardrails" section marked done with the date, and a changelog entry summarizing the new files + expansions. Add the design/plan paths for traceability.

- [ ] **Step 5: Final commit**

```bash
git add todos.md
git commit -m "docs: log content-craft guardrails completion in todos.md

Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
```

---

## Self-Review

**Spec coverage** (each spec section → task):
- §4.1 formatting-and-readability.md → Task 1 ✓
- §4.2 humanization.md → Task 2 ✓
- §4.3 anti-ai-slop expansion (arrows, tells, emoji C3) → Task 3 ✓
- §4.4 conversion-copywriting expansion → Task 4 ✓
- §4.6 pin-spec emoji → Task 5 ✓
- §4.5 agent wiring (content-writer, editor-qa, pinterest-strategist) → Tasks 5/6/7 ✓
- §5 enforcement tiers → Task 7 ✓
- §7 success criteria (planted-violation, no contradiction) → Task 8 ✓

**Placeholder scan:** No TBD/TODO; all file contents are written verbatim. Task 5 step 3 and Task 8 step 4 describe edits in prose rather than a fixed diff because they depend on existing file layout — each names the exact file, location, and content to add, so they are actionable, not placeholders.

**Consistency:** Hard-gate numbers identical across Global Constraints, Task 1, Task 6, Task 7 (≤4 sentences/60 words, ≤35-word sentence, >350-word subhead run, ≤1 bold/paragraph). Arrow set identical across Tasks 3/6/7 (`->`, `→`, `=>`, `»`, `>`-as-arrow). Emoji ban consistent (post + pin) across Tasks 1/3/5/7. Blockquote exemption stated in Global Constraints, Task 3, Task 7, Task 8.
