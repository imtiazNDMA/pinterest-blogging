# Guardrail: Anti-AI-Slop

**Status: hard gate.** "AI slop" = fluent, confident, generic prose that says little, sounds like every
other AI page, and earns nothing. Post-2024 it's a ranking + trust liability (Google helpful-content
signals + reader bounce + Pinterest throttling). A draft that smells of slop **does not ship.**
`editor-qa` runs this as a dedicated kill pass. The content-writer self-applies it before handoff.

This complements `content-quality.md` (which covers E-E-A-T, accuracy, structure). This file is specifically
about **detecting and removing the AI tells.**

---

## A. Banned / red-flag phrasings (delete or rewrite on sight)
**Opener clichés:** "In today's world", "In this day and age", "When it comes to", "Whether you're a
beginner or…", "Let's dive in", "Let's explore", "Look no further", "Picture this".
**Filler connectives & hedges:** "It's important to note", "It's worth noting", "Needless to say",
"As we all know", "Studies show" (without a real cite), "Generally speaking", "In order to" (→ "to").
**LLM signature verbs/nouns:** delve, unleash, elevate, embark, navigate (figurative), leverage, foster,
tapestry, realm, landscape (figurative), testament, treasure trove, game-changer, plethora, myriad,
"a world of", "the perfect [X] for your [Y] needs".
**Empty intensifiers:** "truly", "really", "very", "incredibly", "absolutely", "literally", "undoubtedly".
**Closing slop:** "In conclusion", "At the end of the day", "The possibilities are endless",
"happy gardening!", "with these tips, you'll be well on your way to…".
> A short curated list of these can live nowhere else — keep this section current; add new tells as you spot them.

## B. Structural AI tells (rewrite the structure, not just words)
- **Symmetry/listicle bloat:** every section the same length; every bullet starts the same way; "Rule of three"
  everywhere. Real writing has uneven, intent-driven rhythm.
- **Restating the heading** as the first sentence of its section ("Watering is important for watering.").
- **Defining the obvious** ("A pot is a container you put plants in.").
- **Hedge sandwiches:** "While X can be good, it may depend on various factors, so consider your needs."
  → Make a call. Specific recommendation + the one real caveat.
- **Conclusion that adds nothing** — repeats the intro. Cut it or end on a concrete next action + internal link.
- **Punctuation & sentence-pattern tells** (em-dash overuse, false-contrast constructions): the two most
  frequent and most ignored AI tells. They get their own enforced section — see **Section C** below.
- **Fake personality** bolted on ("As a fellow plant lover, I get it!"): not experience, it's slop cosplay.

## C. Punctuation & sentence-pattern tells (the loudest AI fingerprint)
These are the tells that scream "written by AI" even when the content is good. Enforce hard.

### C1. Em-dashes — strict limit
LLMs spray em-dashes (—) as an all-purpose connector for dramatic pauses, asides, and appositives. A
human gardening writer rarely needs them.
- **Cap: at most ONE em-dash per ~400 words, and only when no cleaner punctuation works.** Most posts should have ZERO.
- Applies to the em-dash `—`, the en-dash used as a connector `–`, and the spaced-hyphen substitute ` - `.
- **Never** use a dash for a dramatic pause or to tack on an afterthought. That's the #1 tell.
- **Rewrite recipes** (do this, don't just delete the dash):
  - Dramatic pause — "It buys you slack — sometimes a whole week." → split: "It buys you slack. Sometimes a whole week."
  - Afterthought — "Use a light mix — never garden soil." → "Use a light mix, not garden soil."
  - Appositive — "the reservoir — a sealed tank — sits below" → parentheses or commas: "the reservoir (a sealed tank below the soil)".
  - List/aside — restructure into its own sentence or a comma clause.
- **Also banned: the emphatic dramatic fragment** used for punch: "full stop", "period.", "simple as that",
  "end of story", "that's it." Just state the point.

### C2. False-contrast / negation-correction constructions
LLMs manufacture drama with a setup-and-subvert template. It's padding that sounds identical across every AI
page. Ban these patterns; state the point directly instead.
- "It's not just X, it's Y" / "This isn't X. It's Y." / "X isn't just about Y, it's about Z"
- "Not only X, but also Y"
- "More than just X" / "X is more than Y"
- "It's not about X. It's about Y."
- "Forget X — meet Y" / "Forget everything you know about X"
- "Think X? Think again." / "Sounds X? It's actually Y."
- "Gone are the days of X" / "Say goodbye to X" / "X? Not anymore."
- **Rhetorical-question fragments** answered immediately: "The result? Healthier roots." / "The best part? …" /
  "The catch? …" / "Why? Because…". (A labeled line like "**The trade-off:** …" is fine; the *question-fragment*
  form is the tell.)
- **Rule of contrast restraint:** at most one genuine, earned contrast per post — and only when the two things
  are really opposed. If you delete the "not X" half and the sentence still works, it was padding.
- **Rewrites:** "Self-watering pots aren't just convenient, they prevent root rot" → "Self-watering pots cut
  watering to twice a week and prevent the flood-then-drought cycle that rots roots."

## D. Substance tells (the deepest, hardest to fake)
- **No specifics:** advice that names no variety, size, number, timing, or threshold. (Cross-ref content-quality.)
- **Hallucination risk:** confident claims with no verifiable source — especially numbers, "studies", plant
  toxicity/edibility. Verify or cut. Never let fluent = true.
- **Says nothing a reader couldn't guess:** if removing the paragraph loses no information, remove it.
- **Generic product blurbs:** "This is a great option for any gardener." → who specifically, why, trade-off.

---

## The de-slop test (editor-qa: each must PASS)
- [ ] Zero banned phrases from section A (or each is justified + rewritten)
- [ ] **Em-dashes within cap** (≤1 per ~400 words, prefer zero); none used as a dramatic pause or afterthought;
      no "full stop"/"period."/"simple as that" emphatic fragments (C1)
- [ ] **No false-contrast constructions** ("not just X, it's Y", "not only… but also", "X? Not anymore",
      rhetorical-question fragments); ≤1 earned contrast in the whole post (C2)
- [ ] No restated headings, obvious definitions, or empty conclusion
- [ ] Section lengths/rhythm vary with intent (no robotic symmetry)
- [ ] Every paragraph carries information a reader couldn't have guessed
- [ ] Every claim is specific OR sourced; no fluent-but-unverified facts
- [ ] No fake/bolted-on personality (real experience only via `[PERSONAL TIP]`, owner-filled)
- [ ] Read aloud: does it sound like a knowledgeable person, not a content mill?

**Verdict:** if 2+ fail, the draft is NEEDS WORK. Rewrite the offending sections; don't surface-patch words.
Em-dash and false-contrast violations are counted by frequency: more than the cap is a single FAIL of that line.

## The rewrite reflex
Don't just delete a banned word. Ask *what was the sentence trying to do?* and rewrite it to do that
concretely. "It's important to water regularly" becomes "Water when the top inch of soil is dry, usually
daily in summer for a 12-inch pot." (Note: no em-dash, no padding — just the specific instruction.)
