# Playbook: Pin Image Generation (brief → finished pin)

Turn the prose design briefs in `Content/pins/<slug>-pins.md` into finished, on-brand 2:3 images ready to
schedule. Obeys `guardrails/ai-image-generation.md`; style from `guidelines/pin-visual-style.md`; prompts from
`templates/ai-image-prompt.md`. This is an **owner step** (you run the AI tool + Canva); the studio gives you
the briefs, prompts, and QA gates.

---

## Inputs
- The pin batch: `Content/pins/<slug>-pins.md` (one block per pin: scene, overlay text, palette, filename, board).
- The four references above (guardrail, style, template, this playbook).
- Tools: an AI image generator (ChatGPT/DALL·E, Gemini/Imagen, or Midjourney) + **Canva** (free) for text.

## Step-by-step (per pin)
1. **Read the brief block.** Note the scene, the overlay text, and the angle.
2. **Pick the archetype** (`pin-visual-style.md` §6). The brief's angle maps to one archetype; confirm no other
   pin in this batch uses the same one.
3. **Choose Path A or B** (`ai-image-prompt.md`):
   - **Path B (default/recommended):** generate a **clean plate, no text** → add text in Canva. Use for any
     multi-word overlay, numbers, badges, or anything that must be crisp/on-brand.
   - **Path A:** let the AI render text only for a **very short ALL-CAPS hero word**, then proofread.
4. **Fill the prompt template** for that archetype: drop in the scene + elements from the brief, append the
   **universal style suffix** and **universal negative prompt**. For Midjourney add `--ar 2:3` (and reuse one
   `--sref`/seed across the whole batch for cohesion).
5. **Generate.** Make 2–4 variants; pick the most authentic, best-composed, best negative-space option.
6. **QA the raw image** against the gate below. Fail → regenerate (tweak the prompt, not just reroll).
7. **Add text in Canva (Path B):** apply brand fonts + overlay band per `pin-visual-style.md` §3–4. Keep text
   ≥80 px from edges; run the thumbnail squint test at ~236 px.
8. **Export** at exactly **1000×1500 px**, `.jpg`, sharp, under ~1 MB. Name the file the brief's suggested
   `<slug>-<descriptor>.jpg`.
9. **Schedule** via the Pinterest **native scheduler** in the evening slot the brief lists; one per day, spaced.
10. **Label the pin AI-generated** in Pinterest's tool (home-decor GenAI opt-out).
11. **Log:** update the pin's `Pin Status` in `pinterest_blog_master_tracker.csv` (Draft → Scheduled → Published)
    and add the real Pin URL when live.

## Image QA gate (every pin, before Canva/export)
- [ ] 2:3 framing, will export 1000×1500, sharp
- [ ] Authentic: no warped railings, melted lights, extra fingers, CGI sheen, oversaturation
- [ ] Correct small-balcony scale; right-season, living plants
- [ ] No logos / watermarks / real identifiable people / copyrighted art
- [ ] Negative space present for the text (Path B) OR hero word renders cleanly + proofread (Path A)
- [ ] On-palette, matches the batch's other pins (cohesion)
- [ ] Before/after = same space + angle, honest transformation
- [ ] No prices / "cheapest" / stock text on the image; no emojis
- [ ] Does not contradict any plant/pet safety claim in the post

## Batch cohesion pass (after all pins generated)
Lay the 4–6 finished pins side by side:
- One palette, one font pairing, one brand-mark treatment across all.
- **≥4 distinct archetypes**; every crop/perspective different; every overlay a different hook.
- If two pins could be confused for each other, redesign one (near-duplicates aren't "fresh" pins).

## Troubleshooting
| Problem | Fix |
|---|---|
| Text is garbled / misspelled | Switch to Path B: regenerate a clean plate, add text in Canva |
| Railings/architecture warped | Add to negative prompt; specify "straight apartment railing, correct perspective"; reroll |
| Looks like CGI / too perfect | Add "authentic photograph, lived-in, soft natural light, slight imperfection"; lower stylize |
| Wrong aspect ratio | Force 2:3 (`--ar 2:3` / "vertical 1024×1536"); never crop a landscape into 2:3 and lose the composition |
| Pins look too similar | Change archetype + crop + overlay; vary the hero subject |
| Faces look off | Avoid faces — use hands, backs, or no people |
| Tropical plant on a "winter" pin | Name the season + hardy/dormant plants explicitly; add wrong-season plants to negative |

## Where this sits in the pipeline
`/make-pins <slug>` (pinterest-strategist) writes the briefs → **this playbook** turns briefs into images →
schedule + publish → `/weekly-review` reads which designs earn saves/clicks and feeds winners back into the
next batch's archetype/overlay choices.
