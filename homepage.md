# Homepage Build Guide — Bloom & Lantern ("Golden Hour")

> Paste-ready, block-by-block build for the **static homepage**, using the **Kadence theme + Kadence Blocks (free)** and core WordPress blocks. Nothing here needs a paid plugin or page builder.
> Brand system (palette, fonts, CSS, header, footer) is already defined in `Growth Strategy/kadence-theme-spec.md` — **apply that first**, then build this page. This doc only covers the homepage body; the header and the dusk-blue footer come from the theme spec.
> Owner builds this in WordPress (I can't log in). Build top to bottom; each section is one Kadence **Row Layout** block.

---

## What you need first (all free)
- **Kadence theme** (active) + **Kadence Blocks** plugin (free) — gives Row Layout, Advanced Heading, Advanced Button, Info Box, Icon.
- The brand system from `kadence-theme-spec.md` already applied (fonts, palette, header, footer, Additional CSS).
- A few posts published and assigned to the **Balcony Ideas** / **Patio Ideas** categories (so the Latest grid + links resolve).
- 4 images you generate from the prompts in the appendix (1 hero + 2 space cards + 1 about). Save as JPG, upload to Media Library before building.

## Decisions baked into this build
- **Hero:** AI golden-hour image + lower-third cream band (mirrors your Aesthetic Hero pins).
- **Homepage's #1 job:** send readers into the **Balcony hub** and **Patio hub** (pageview depth → Mediavine path).
- **No email band yet** (add later when a provider is connected).
- **No on-page Pinterest strip** — your Pinterest + socials live in the dusk-blue footer.

## Palette + type quick-reference (from the theme spec)
| Token               | Hex       | Use                        |
| ------------------- | --------- | -------------------------- |
| Terracotta (accent) | `#C97B5A` | primary buttons, accents   |
| Terracotta dark     | `#A85F42` | button hover               |
| Heading             | `#2E2B27` | H1–H3                      |
| Body                | `#3A3A38` | paragraphs                 |
| Muted               | `#6B655C` | eyebrows, meta             |
| Border              | `#E4D6BF` | hairlines, card borders    |
| Subtle bg           | `#EFE3D1` | alt-section background     |
| Base bg (cream)     | `#F5EBDD` | page background, hero band |
| Dusk blue           | `#2C3E50` | footer (theme spec)        |
| Sage                | `#9CAF88` | Patio card tint            |
| Honey               | `#C8A06A` | Balcony card tint          |
| Amber               | `#E8B86D` | glow accents               |
| Content surface     | `#FFFDF8` | card surfaces              |

**Fonts:** Playfair Display (headings) · Montserrat (body, eyebrows, buttons). **Eyebrow style:** Montserrat, UPPERCASE, letter-spacing 0.12em, ~13px, color terracotta-dark `#A85F42`. (The theme spec's Additional CSS already defines an `.eyebrow` class — apply it via the Advanced Heading "Advanced → Additional CSS class" field, or just set those values inline.)

---

## STEP 0 — Create the page and strip the chrome

1. **Pages → Add New** → title it `Home`. Publish (empty for now).
2. **Settings → Reading → Your homepage displays → A static page → Homepage = Home.** Set **Posts page = Blog** (create a `Blog` page if you want a dedicated feed; optional).
3. Open `Home` to edit. In the right-hand **Page → Kadence** settings panel set:
   - **Title:** Hide / Disable (the homepage shouldn't show an H1 page title — the hero H1 is the page H1).
   - **Content Width:** **Full Width**.
   - **Disable Content Padding / Spacing:** ON (so sections run edge to edge).
   - **Transparent Header:** optional — turn ON only if you want the hero image to run under the header. Looks great with the hero; if the nav becomes hard to read, leave it OFF.

> Global rule for every section below: each is a **Kadence Row Layout** block. Set **Structure → Content Max Width = 1080px** (keeps text readable on wide screens) and **Padding: Desktop 80px top / 80px bottom, Mobile 48 / 48**. Vary backgrounds as noted so sections alternate gently.

---

## SECTION 1 — Hero

**Goal:** one glance that says "small balcony & patio styling," then two buttons into the hubs.

**Block tree**
```
Row Layout (Hero)
└─ Single column, content vertical-align: BOTTOM, horizontal: LEFT
   └─ Inner container (the cream band)
      ├─ Advanced Heading  (eyebrow)
      ├─ Advanced Heading  (H1)
      ├─ Paragraph         (subhead)
      └─ Buttons (Kadence Advanced Button ×2)
```

**Row settings**
- Structure: **Full Width**. **Min Height: 75vh** (Desktop), 70vh (mobile). Content Max Width 1080px.
- **Background → Image:** your hero JPG (appendix A1). Size: Cover. Position: center.
- **Background Overlay:** Gradient, `transparent` at top → `rgba(44,62,80,0.45)` at bottom (angle 180°). This darkens the lower third so the band and text stay legible.
- Column vertical align: **Bottom**. Padding bottom 56px.

**The cream band (inner container)** — a nested Kadence **Column / Section** inside the column:
- Background: `#F5EBDD` at **94% opacity**. Border-radius **10px**. Padding 32px (mobile 24px). Max width **620px**. Box shadow: soft (0 10px 30px rgba(0,0,0,.12)).

**Copy (paste in)**
- **Eyebrow** (Advanced Heading, tag = `span` or `p`, `.eyebrow` style): `SMALL BALCONY & PATIO STYLING`
- **H1** (Advanced Heading, tag **H1**, Playfair 700, 44px desktop / 30px mobile, color `#2E2B27`):
  `Make the most of your small balcony or patio`
- **Subhead** (Paragraph, Montserrat 400, 18px, color `#3A3A38`):
  `Renter-friendly decor, furniture, privacy, garden, and lighting ideas for the small space you already have. No backyard, no drills, no overspending.`
- **Button 1 — primary** (filled): label `Explore Balcony Ideas` → link `/small-balcony-patio-ideas`. Background `#C97B5A`, text `#FFF8EF`, radius 6px, padding 14×28.
- **Button 2 — outline** (secondary): label `Explore Patio Ideas` → link `/small-patio-ideas`. Transparent bg, border + text `#A85F42`, hover fills `#C97B5A`.
- Button gap: 12px. On mobile they stack full-width.

---

## SECTION 2 — Start with your space (two cards)

**Goal:** instantly route the visitor by their space. Two big, tappable cards.

**Block tree:** Row Layout (2 columns, equal) → each column an **Info Box**.

**Row settings:** Background `#F5EBDD` (cream). Column gap 24px. On mobile, columns stack.

**Optional section heading** above the cards (Advanced Heading, centered): H2 `Start with your space` (Playfair 32px, `#2E2B27`). Keep it short or omit — the cards speak for themselves.

**Card A — Balcony** (Info Box)
- Media: image (appendix A2a) **or** a leaf/railing icon; if image, top-of-card, 3:2 crop.
- Container background: **honey tint** — `#C8A06A` at 14% (or `#F3E7D2`). Border 1px `#E4D6BF`. Radius 10px. Padding 28px. **Hover:** lift 2px + soft shadow (Kadence Info Box → Container → Hover).
- Title (H3, Playfair 24px): `Balcony Ideas`
- Text (Montserrat 16px): `Up high on a railing? Style a cozy, modern, or boho balcony that works in inches, not acres.`
- Learn-more link/button: `Browse balcony ideas →` (use text "Browse balcony ideas", the theme CSS adds the warm underline; skip literal arrow) → `/small-balcony-patio-ideas`. Make the **whole box clickable** (Info Box → Link → "Apply link to entire box").

**Card B — Patio** (Info Box)
- Container background: **sage tint** — `#9CAF88` at 16% (or `#E8EDE0`). Same border/radius/padding/hover.
- Title (H3): `Patio Ideas`
- Text: `Down at ground level? Turn a bare slab or tight patio into a full outdoor room you actually use.`
- Link (entire box) → `/small-patio-ideas`. Label `Browse patio ideas`.

---

## SECTION 3 — Start here (curated guides)

**Goal:** give first-time visitors your 4 strongest entry points (the hubs + the biggest-volume + the money post).

**Block tree:** Row Layout → Advanced Heading (eyebrow + H2) → Row Layout (4 columns) → 4 × Info Box.

**Row settings:** Background `#FFFDF8` (content surface, a subtle lift off the cream). 4 columns desktop → 2 tablet → 1 mobile.

**Heading block**
- Eyebrow (`.eyebrow`): `START HERE`
- H2 (Playfair 32px, `#2E2B27`): `New here? Start with these`

**The 4 cards** (Info Box each: featured image top 3:2, title H3 18px, one line, entire box links):
| Card | Title | One-liner | Link |
|---|---|---|---|
| 1 | Small Balcony Ideas | The complete small-balcony playbook, in one guide. | `/small-balcony-patio-ideas` |
| 2 | Small Patio Ideas | Thirty ways to style a tiny patio or slab. | `/small-patio-ideas` |
| 3 | Balcony Garden Ideas | Grow a lush container garden on a railing. | `/balcony-garden-ideas` |
| 4 | Best Small-Patio Furniture | Seating that fits where it seems impossible. | `/patio-furniture-ideas` |

- Card container: `#FFFDF8`, border 1px `#E4D6BF`, radius 10px, hover lift. Use each post's **featured image** (upload or reuse a pin plate).

---

## SECTION 4 — Find your project (browse by topic)

**Goal:** let visitors self-route by the six things you cover, regardless of balcony vs patio.

**Block tree:** Row Layout → Advanced Heading (H2 + subhead) → Row Layout (3 columns) → 6 × Info Box (icon style), arranged 3 across × 2 rows.

**Row settings:** Background `#F5EBDD` (cream). 3 cols desktop → 2 tablet → 2 mobile (small tiles read fine 2-up on phones).

**Heading**
- H2 (Playfair 32px): `Find your project`
- Subhead (Montserrat 16px, `#6B655C`, centered): `Six things to sort out for any small outdoor space. Tap the one you're working on.`

**The 6 tiles** (Info Box, **Icon** media — Kadence's free icon library; icon color terracotta `#C97B5A`, size 36px; title Montserrat 600 16px caps optional; entire box links):
| Tile | Suggested Kadence icon | Link |
|---|---|---|
| Decor & Styling | `palette` / `image` | `/small-balcony-patio-ideas` |
| Furniture & Seating | `chair` / `bx-chair` | `/patio-furniture-ideas` |
| Privacy & Shade | `shield` / `fence` | `/balcony-privacy-ideas-for-apartments` |
| Garden & Plants | `leaf` | `/balcony-garden-ideas` |
| Flooring | `grid` / `square` | `/balcony-flooring-ideas` |
| Lighting | `bulb` / `sun` | `/balcony-lighting-ideas` |

- Tile container: `#FFFDF8`, border 1px `#E4D6BF`, radius 10px, padding 24px, centered content, hover lift + icon color → `#A85F42`.

> As you publish the remaining pillars (e.g. the Balcony Furniture money pillar), you can repoint Furniture to a dedicated balcony-furniture hub. For now every tile lands on a strong, live hub.

---

## SECTION 5 — About teaser

**Goal:** a warm, trust-building line about who this is for (also helps Google E-E-A-T and ad-network review).

**Block tree:** Row Layout (2 columns, ~45% image / 55% text, vertical-align center) → col 1 Advanced Image; col 2 Advanced Heading (eyebrow + H2) + Paragraph + Advanced Button.

**Row settings:** Background `#EFE3D1` (subtle deeper cream, sets the section apart). On mobile, image stacks above text.

**Col 1 — image:** appendix A4 (a warm, lived-in corner). Radius 10px.

**Col 2 — copy**
- Eyebrow (`.eyebrow`): `OUR STORY`
- H2 (Playfair 32px): `Small space, big potential`
- Body (Montserrat 16px, `#3A3A38`):
  `You have a small balcony or patio, a limited budget, and probably a lease that says "no permanent changes." Bloom & Lantern is built for exactly that. We turn tight outdoor spaces into corners you actually want to sit in, with clear, renter-friendly ideas you can copy this weekend.`
- Button (outline): `About Bloom & Lantern` → `/about`.

---

## SECTION 6 — Latest from the blog

**Goal:** show the site is active and feed fresh pageviews. Fully dynamic and free via the core **Query Loop** block (no Kadence Pro needed).

**Block tree:** Row Layout → Advanced Heading (H2) → core **Query Loop** → (Post Template: Featured Image + Post Terms + Post Title) → optional Advanced Button.

**Row settings:** Background `#F5EBDD` (cream). Content max width 1080px.

**Heading:** H2 (Playfair 32px, centered): `Latest from the blog`

**Query Loop setup**
- Insert **Query Loop** → choose a starting pattern with image + title, or build it: inside the Post Template add **Featured Image** (link to post, aspect ratio 3:2), **Post Terms → Categories** (style as eyebrow: Montserrat caps, `#A85F42`, 12px), **Post Title** (link, Playfair 20px, `#2E2B27`).
- Query settings: **Inherit = OFF**, Post type = Posts, **Order by = Date / Newest**, **Items = 6**.
- Layout: **Grid, 3 columns** (Display settings on the Query Loop block) → 2 tablet → 1 mobile. Column gap 24px, row gap 32px.
- Card polish (optional): wrap each in a Group with background `#FFFDF8`, border `#E4D6BF`, radius 10px, padding 0 0 16px (image flush to top, text padded).

**Optional button** under the grid (outline, centered): `View all guides` → your Blog page (or a category archive).

> If your Kadence Blocks version includes the **Posts** block, you may use it instead for easier styling — but Query Loop is guaranteed-free and does the job.

---

## Apply order (fastest path)
1. STEP 0 — create `Home`, set static homepage, disable title + go full-width.
2. Generate + upload the 4 images (appendix).
3. Build Section 1 (Hero) → preview on mobile before moving on (the band + buttons are the fussiest part).
4. Sections 2 → 6 in order. Save as a **Kadence pattern** after each looks right, so you can reuse the card styles.
5. Final pass: check spacing rhythm (every section 80/80 desktop), alternating backgrounds (cream → cream → surface → cream → deep-cream → cream), and that every link resolves.

## Quality + accessibility floor
- **Contrast:** charcoal/heading on cream and terracotta buttons with cream text all pass WCAG AA. Keep terracotta for buttons/large text, not small body copy.
- **One H1 only:** the hero H1. Everything else is H2/H3. (That's why STEP 0 disables the page title.)
- **Mobile:** test the hero at 70vh — if the band crowds, drop H1 to 28px and let buttons stack full-width. Cards should be 1-up (sections 2/3) or 2-up (section 4) on phones.
- **Speed:** images compressed (use a free optimizer / WebP), fonts loaded locally + preloaded (theme spec §0). Lazy-load everything below the hero.
- **No em-dashes, no emoji, no arrows in on-page copy** — matches house style. (The "→" in this doc is shorthand for *links to*, not literal page text.)

---

## Appendix A — AI hero + section image prompts
Generate at the sizes noted, in the house palette, photographic and authentic (same direction as your pins, Path B style). These run on **your own site**, so the Pinterest AI-label rule doesn't apply here; your About page already discloses the site is AI-assisted.

**A1 — Hero (wide, ~2000×1100, 16:9-ish; keep the lower-left calm for the cream band)**
```
A fully styled small balcony at golden hour, shot wide and slightly low: a cushioned low-profile chair
with a throw, layered potted greenery along a real railing, warm-white string lights glowing overhead,
a small side table with a cup. Warm, lived-in, aspirational. Leave the lower-left third calm and
uncluttered as negative space for a text band.
Style: warm soft natural golden-hour light, editorial home-decor photography, authentic and photographic,
cozy, lived-in. Palette: warm cream, honey wood, terracotta, sage green, soft charcoal, amber glow, dusk-blue
sky. Composition: rule of thirds, real depth, intentional negative space lower-left. Realistic apartment
balcony scale with a real railing. High resolution, ~16:9.
Negative: warped or impossible architecture, warped railing, melted or doubled string lights, floating
furniture, extra fingers, distorted faces, gibberish text, CGI plastic sheen, oversaturation, HDR halos,
fisheye, watermark, brand logos, on-image prices, dead or wrong-season plants, clutter.
```

**A2a — Balcony space card (square ~1000×800, 5:4)**
```
A cozy styled corner of a small apartment balcony with a real railing: a low chair with a warm throw, a
couple of leafy potted plants, a small lantern. Inviting, warm, uncluttered.
Style: warm golden-hour editorial home-decor photography, authentic, cozy. Palette: cream, honey wood,
terracotta, sage, soft charcoal, amber. Realistic balcony scale, real railing. ~5:4.
Negative: warped railing, melted lights, floating furniture, gibberish text, plastic CGI sheen, logos,
prices, dead plants, clutter, fisheye.
```

**A2b — Patio space card (square ~1000×800, 5:4)**
```
A styled small ground-level patio corner: a compact two-seater with a cushion and lumbar pillow on a paved
slab, a flatweave outdoor rug, a couple of potted plants, a fence or low wall behind, soft string lights.
No balcony railing. Warm and inviting.
Style: warm golden-hour editorial home-decor photography, authentic, cozy. Palette: cream, honey wood,
terracotta, sage, soft charcoal, amber. Ground-level patio scale (slab, fence or low wall, no railing). ~5:4.
Negative: balcony railing high above ground, warped fence, melted lights, floating furniture, gibberish text,
plastic CGI sheen, logos, prices, dead plants, clutter, fisheye.
```

**A4 — About teaser image (~1200×900, 4:3; lived-in, human warmth)**
```
A warm, lived-in small outdoor corner at dusk: a comfortable styled seat with a folded throw and a book, a
mug, soft string-light glow, a few healthy plants. Cozy, personal, real. No people required.
Style: warm dusk editorial home-decor photography, authentic, intimate. Palette: cream, honey wood,
terracotta, sage, soft charcoal, amber glow, dusk blue. Realistic small balcony or patio scale. ~4:3.
Negative: warped architecture, melted lights, floating furniture, gibberish text, plastic CGI sheen, logos,
prices, dead plants, clutter, fisheye.
```

---

## Appendix B — Copy block (for fast paste)
- **Eyebrow (hero):** SMALL BALCONY & PATIO STYLING
- **H1:** Make the most of your small balcony or patio
- **Subhead:** Renter-friendly decor, furniture, privacy, garden, and lighting ideas for the small space you already have. No backyard, no drills, no overspending.
- **Hero buttons:** Explore Balcony Ideas · Explore Patio Ideas
- **Section 2 H2:** Start with your space
- **Balcony card:** Balcony Ideas — Up high on a railing? Style a cozy, modern, or boho balcony that works in inches, not acres.
- **Patio card:** Patio Ideas — Down at ground level? Turn a bare slab or tight patio into a full outdoor room you actually use.
- **Section 3:** START HERE / New here? Start with these
- **Section 4:** Find your project / Six things to sort out for any small outdoor space. Tap the one you're working on.
- **Section 5:** OUR STORY / Small space, big potential / [About body above] / About Bloom & Lantern
- **Section 6:** Latest from the blog / View all guides
