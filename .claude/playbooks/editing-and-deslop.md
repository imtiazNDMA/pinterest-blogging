# Playbook: Editing & De-Slop Pass

The repeatable edit that turns a raw draft into high-quality, converting content. The content-writer
self-runs a light version before handoff; **editor-qa runs the full version** in `/new-post`.

References: `guardrails/anti-ai-slop.md`, `guardrails/content-quality.md`, `guidelines/headlines-and-titles.md`,
`hooks-and-intros.md`, `conversion-copywriting.md`, `seo-rules.md`, `affiliate-compliance.md`.

## Pass order (cheap structural fixes first, polish last)
1. **Intent & promise** — does the post deliver exactly what the title/intent promised? If not, fix scope first.
   (`hooks-and-intros.md` + `content-quality.md`)
2. **De-slop pass** — run the `anti-ai-slop.md` test. Delete banned phrasing; fix structural tells (restated
   headings, robotic symmetry, empty conclusion, hedge sandwiches); **rewrite, don't surface-patch.**
3. **Specificity pass** — every vague claim gets a number/variety/size/threshold or gets cut. Flag any claim
   that's fluent-but-unverified; verify (WebSearch) or remove. Plant/pet safety: verify or hedge + cite.
4. **Hook & title pass** — intro mirrors intent, answer-first, quick-answer block present; titles follow
   `headlines-and-titles.md` (keyword front-loaded, specific, deliverable). Tighten the meta description.
5. **Conversion pass (buyer posts)** — verdict-first picks, selection criteria, "best for…" segmentation,
   honest trade-offs, descriptive-anchor CTAs, comparison table — all compliant (no prices, disclosure placed).
6. **SEO & links pass** — primary keyword placement (no stuffing), heading hierarchy, ≥3 internal links,
   image alt/filenames.
7. **Read-aloud pass** — does it sound like a knowledgeable person, not a content mill? Fix rhythm; cut filler.
8. **Placeholder check** — `[PERSONAL TIP]`/`[YOUR PHOTO]` left for the owner, never auto-filled.

## Output
- Apply safe fixes directly; for substantive rewrites, fix accurately or flag the exact location + instruction.
- Verdict: **READY** (every gate passes → set frontmatter `status: ready`) or **NEEDS WORK** (list what blocks it).
- Note anything the owner must resolve (fill a `[PERSONAL TIP]`, supply a photo, confirm a local claim).

## The one rule that matters most
If a section could appear unchanged on 50 other gardening blogs, it is slop — rewrite it with specifics or
delete it. Volume without quality fails this whole business model.
