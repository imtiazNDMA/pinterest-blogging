# Guardrail: AI Image Generation (Pins & Blog Images)

**Status: hard rules.** Applies to every AI-generated image — pins, blog hero/in-body images, social.
Companion craft spec: `guidelines/pin-visual-style.md`. Procedure: `playbooks/pin-image-generation.md`.
Prompts: `templates/ai-image-prompt.md`. Pin copy/strategy: `guardrails/pinterest-policy.md`.

When a rule here conflicts with a request, **surface the conflict — do not silently ship a violating image.**

## 1. Format (non-negotiable)
- **Pins: strict 2:3 vertical, exported at 1000×1500 px.** No square, no landscape, no other ratio.
- Blog in-body images: 3:2 or 4:3 landscape is fine; hero can be 16:9. Pins are always 2:3.
- Final file is sharp (no upscale mush), under ~1 MB where possible, `.jpg` for photos / `.png` only if it needs transparency.

## 2. Truthful & non-misleading (Pinterest trust + FTC adjacency)
- The image must **match the destination post**. No bait, no "magazine vs slum" exaggeration, no implying a result the post doesn't deliver.
- **Before/after splits must be the same space, same camera angle**, a realistic transformation. No fake dramatic swap.
- **No invented proof:** no fake "as seen on," no fabricated awards/ratings/review stars, no fake screenshots or fake UGC.
- **No prices, "cheapest," discounts, or stock claims rendered on the image** (mirrors Amazon ToS + `affiliate-compliance.md`).

## 3. Label AI honestly
- **Every AI image is labeled AI-generated when published on Pinterest.** Home decor is on Pinterest's 2026 GenAI "see less" opt-out list — undisclosed AI risks distribution and trust. Gardening is exempt, but label anyway for consistency.
- Keep renders **authentic** (see §4) so the label costs nothing; uncanny + unlabeled is the worst case.

## 4. Realism floor (reject if any are present)
Kill and regenerate any image showing:
- Warped / impossible **architecture or railings**, melted or doubled string lights, floating furniture.
- **Anatomy errors**: extra or fused fingers/limbs, distorted faces, mismatched eyes (avoid close-up faces entirely where possible).
- **Garbled, misspelled, or gibberish text** baked into the image (see §5 — prefer adding text in Canva).
- Plastic/CGI sheen, over-saturation, HDR halos, fisheye distortion, obvious tiling/clone artifacts.
- **Plants that misrepresent the niche** (tropical houseplants on a "winter balcony", dead plants in an "after").

## 5. Text on the image
- **Default to Path B** (`playbooks/pin-image-generation.md`): generate a clean image plate, add overlay text in **Canva** with brand fonts. AI text rendering is unreliable, especially for multi-word or small text.
- If you let the AI render text (Path A), it is allowed **only for very short, ALL-CAPS hero words** and must be **proofread letter-by-letter** before publishing. Any garble → Path B.
- **Zero emojis** on the image, in overlay text, or in pin copy (mirrors `anti-ai-slop.md` C3 + `pin-spec.md`).

## 6. No third-party IP
- **No brand logos, trademarks, watermarks, or signatures** in the image (no Amazon/Wayfair/IKEA marks, no fake brand tags).
- No recognizable copyrighted characters, art, or real identifiable people. Models are generic/non-identifiable.
- No stock-site watermarks; don't prompt "in the style of [living artist]".

## 7. Brand & safety consistency
- Stay inside the house palette + layout system (`guidelines/pin-visual-style.md`) so the account reads as one authority.
- Image content must not contradict a **safety/YMYL** claim in the post (e.g., don't show a pet beside a plant the post flags as toxic).
- Bootstrap budget: free / already-paid tools only unless the owner approves a cost (`CLAUDE.md` rule 7).

## Pre-publish checklist (every AI image)
- [ ] 2:3 / 1000×1500 (pin) and sharp
- [ ] Matches the destination post; before/after honest; no fake proof
- [ ] No prices / "cheapest" / stock text on the image
- [ ] No garbled text; overlay text proofread (or added in Canva)
- [ ] No warped architecture, anatomy errors, or CGI sheen
- [ ] No logos / watermarks / real people / copyrighted characters
- [ ] On-palette, on-template; no emojis
- [ ] Does not contradict any plant/pet safety claim in the post
- [ ] Will be **labeled AI-generated** on Pinterest
