# Guideline: Pin Visual Style (the design system)

**What "good" looks like for every pin and blog image.** This is the craft layer; hard rules live in
`guardrails/ai-image-generation.md`, copy/angles in `guidelines/pin-spec.md`. Generate with
`templates/ai-image-prompt.md`, follow `playbooks/pin-image-generation.md`.

Goal: a scroll-stopping, **cohesive, authentic** look so the whole account reads as one trusted
authority on Balcony & Patio Styling. Same DNA, different outfit on every pin.

---

## 1. Brand visual identity (the feeling)
Warm, cozy, lived-in, aspirational-but-attainable. Editorial home-decor photography, **not** stock-cheesy,
**not** uncanny CGI. The viewer should think "I could make my balcony feel like that," then click to find out how.

Mood words to put in prompts: *warm, soft natural light, golden hour, cozy, inviting, lived-in, styled,
editorial, photographic, authentic.*

---

## 2. Color palette
Use a warm, earthy decor palette. Hex values are the default house set (swap once a brand is finalized).

| Role | Color | Hex | Use |
|---|---|---|---|
| Neutral base | Warm cream / oat | `#F5EBDD` | Backgrounds, text bands |
| Warm neutral | Honey wood | `#C8A06A` | Wood tones, secondary fills |
| Primary accent | Terracotta / clay | `#C97B5A` | Headlines, badges, accent objects |
| Secondary accent | Sage / olive | `#9CAF88` | Plants, supporting labels |
| Dark / text | Soft charcoal | `#3A3A38` | Text on light, contrast |
| Glow | Amber (golden hour) | `#E8B86D` | String lights, warm light sources |
| Depth | Deep dusk blue | `#2C3E50` | Dusk skies, high-contrast bands |

**60-30-10 rule:** ~60% warm neutral (cream / wood / concrete), ~30% supporting (sage / charcoal /
dusk), ~10% punch (terracotta / amber). Keep every pin in this family so a batch looks like a set.

---

## 3. Typography & font selection
**Two families per pin, max** (a third only as a tiny accent). One display for the hook, one clean sans
for sub-text/labels/CTA. All recommendations are **free** (Google Fonts + Canva), per the bootstrap budget.

| Slot | Default font | Alt (punchy) | Notes |
|---|---|---|---|
| Display / hero word | **Playfair Display** (serif, editorial, warm) | **Bebas Neue** (tall condensed caps) | Bebas for big numbers / list pins |
| Body / labels / CTA | **Montserrat** (geometric sans) | **Poppins** or **Nunito Sans** | Clean, legible at small size |
| Accent (rare) | **Caveat** (handwritten) | **Sacramento** | One word only (e.g., "cozy"); never a whole line |

**Hierarchy & sizing** (on the 1000×1500 canvas):
- Hero headline: **90–160 px**. Subhead: **40–60 px**. Labels / tags: **28–40 px**. Brand mark: **24–30 px**.
- **Minimum legible size ≈ 28 px.** Below that it disappears at thumbnail scale.
- One focal message per pin; hero overlay **≤ 8 words**. Don't fill the pin with text.

**Case & emphasis:**
- ALL CAPS for short hero overlays, list numbers, and corner badges. Title Case for longer lines.
- Letter-spacing +2–5% on caps for a premium feel. Avoid italics except the handwritten accent.
- Pick ONE word to emphasize (color or size), not three. (Mirrors the ≤1-emphasis discipline in the post rules.)

---

## 4. Text-overlay system
Text must survive the **thumbnail squint test** (legible at ~236 px wide, the Pinterest feed size).

**Always put a band / scrim behind text over a photo** — never raw text on a busy image.

| Overlay style | When | Spec |
|---|---|---|
| Lower-third band | Aesthetic hero | Cream band, ~85–90% opacity, bottom third; charcoal text |
| Top band | Search-match | Solid/again ~90% band across upper third; high contrast |
| Center badge | Category / hub | Circle or square, terracotta or charcoal fill, white text |
| Seam banner | Before/after, split | Full-width band across the middle seam; bold short text |
| Corner tag | Feature call-out | Small pill (e.g., "NO DRILL"); flat color, white text |

- **Coverage:** text + bands ≤ ~40% of the pin; leave ~60% breathing room for the image.
- **Safe margins:** keep all text ≥ **80 px** from every edge (Pinterest rounds corners and crops).
- **Contrast:** dark-on-cream or white-on-charcoal/terracotta; aim ~4.5:1 (WCAG AA) for thumbnail legibility.
- **Brand mark:** small {{BLOG_NAME}} wordmark, bottom-center or bottom-corner, 24–30 px, low-key.

---

## 5. Photographic realism standards
The single biggest differentiator vs generic AI pins. Aim for believable editorial decor photography.

- **Lighting:** warm, soft, directional — golden hour, blue-hour glow, or window light. Avoid flat HDR / harsh flash.
- **Composition:** rule of thirds, a clear focal point, real depth, and **intentional negative space** for the text.
- **Authenticity cues:** real textile folds, true-to-life bulb glow, correct railing perspective, natural plant
  textures, a little lived-in imperfection. A slightly messy throw beats a showroom.
- **Scale truth:** small balconies look small — narrow ledges, apartment railings, compact furniture. Don't render a terrace.
- **Reject** (see `guardrails/ai-image-generation.md` §4): warped railings, melted lights, extra fingers,
  CGI sheen, over-saturation, garbled text, wrong-season or dead plants.
- **Faces:** avoid close-up faces; prefer hands, backs, or no people. Generic, non-identifiable only.

---

## 6. Layout archetypes (the "packaging")
Each pin is built from one archetype. **Never use the same archetype twice in one batch** — varied layout is
what makes each pin a *fresh* pin (Pinterest rewards fresh, penalizes near-duplicates).

| # | Archetype | Proportion | Best for |
|---|---|---|---|
| 1 | **Aesthetic Hero** | Full-bleed photo + lower-third band | Flagship save-magnet, mood/aspiration |
| 2 | **Number / List Grid** | 2×3 or 3×3 vignettes + big number header | "X ideas" listicles |
| 3 | **Before / After Split** | Vertical 50/50 top/bottom + seam banner + tags | Makeovers, transformations |
| 4 | **Comparison Split** | Left/right halves + label per side | Spend-vs-save, this-vs-that, curiosity |
| 5 | **Category Quadrant** | 2×2 labeled vignettes + center badge | Hub/overview breadth (pillar) |
| 6 | **Formula / Diagram Stack** | Vertical numbered steps + photo strips | Frameworks, "the X-step formula" |
| 7 | **Text-Forward Tease** | Soft/blurred photo strip + large cream headline panel + small badge | Curiosity, "without losing your deposit" |
| 8 | **Single Product / Flat-lay** | One item or tidy flat-lay + label | Product pins, buyer intent |

---

## 7. Batch packaging (cohesion + freshness)
A batch = the 4–6 pins for one post. The art of "packaging" is making them feel like a **set** while staying **distinct**.

**Shared across the batch (the DNA):** palette, font pairing, brand-mark style/position, overall warm mood.

**Varied across the batch (the freshness):** layout archetype, overlay text + angle, crop / camera perspective,
hero subject. Map angles → archetypes so no two pins look alike:

| Angle (from `pin-spec.md`) | Default archetype |
|---|---|
| Aesthetic / mood | Aesthetic Hero (1) |
| List / number | Number Grid (2) |
| Before/after | Before/After Split (3) |
| Budget / comparison | Comparison Split (4) |
| Category / hub | Category Quadrant (5) |
| Formula / curiosity | Formula Stack (6) or Text-Forward Tease (7) |
| Product / buyer | Single Product (8) |

**Batch cohesion checklist:** one palette, one font pairing, one brand-mark treatment, ≥4 distinct archetypes,
each crop/perspective different, every overlay a different hook. If two pins could be mistaken for each other, redesign one.
