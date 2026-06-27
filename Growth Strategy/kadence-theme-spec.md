# Kadence Theme Customization — Bloom & Lantern ("Golden Hour")

> Paste-ready spec for the Kadence theme so the site matches the pin design system (one brand across site + pins).
> Apply in **Appearance → Customize** unless noted. Brand palette + fonts come from `.claude/guidelines/pin-visual-style.md`.
> Signature moves: **dusk-blue footer** (lantern at dusk) + **amber glow** on buttons/links (the lantern warming up).
> Keep everything else quiet so those two land. Owner applies these in WordPress; I can't log in.

---

## 0. Fonts (do this first)
Kadence loads Google Fonts natively in every typography selector, so **no font plugin needed**.
- Display / headings: **Playfair Display** (weights 600, 700)
- Body / UI / buttons: **Montserrat** (weights 400, 500, 600)
- (Pins also use **Bebas Neue** for big numbers; not needed on the site.)
- Performance: **Customize → General → Performance → Load Fonts Locally = ON**, **Preload = ON**. Only the weights above — don't load the full families.

---

## 1. Global color palette
**Customize → General → Colors → Palette.** Click each swatch and set the hex. Roles map to Kadence's 9 slots:

| Slot | Role | Hex | Used for |
|---|---|---|---|
| 1 | Accent | `#C97B5A` | links, buttons, accents (terracotta) |
| 2 | Accent 2 (hover/active) | `#A85F42` | button hover, link hover (darker terracotta) |
| 3 | Strongest text / headings | `#2E2B27` | H1–H3 (warm near-black) |
| 4 | Base text / body | `#3A3A38` | paragraph text (charcoal) |
| 5 | Muted text | `#6B655C` | meta, captions |
| 6 | Border / hairline | `#E4D6BF` | dividers, table & card borders |
| 7 | Subtle background | `#EFE3D1` | alt sections, sidebar, cards (deeper cream) |
| 8 | Base background | `#F5EBDD` | page background (cream) |
| 9 | Dark background | `#2C3E50` | footer (dusk blue) |

**Brand extras** (not in the 9 slots; used via the CSS in §8): sage `#9CAF88`, honey `#C8A06A`, amber `#E8B86D`, content surface `#FFFDF8`.

60-30-10 in practice: ~60% cream/wood neutrals, ~30% charcoal/sage/dusk, ~10% terracotta/amber punch. Don't let terracotta spread past accents.

---

## 2. Typography
**Customize → General → Typography.**

**Base (body):** Montserrat · weight 400 · size **17px** desktop / 16px mobile · line-height **1.75** · letter-spacing 0 · color slot 4.

**Headings:**
| Tag | Font | Weight | Size (desktop / mobile) | Line-height | Letter-spacing | Transform |
|---|---|---|---|---|---|---|
| H1 | Playfair Display | 700 | 44 / 30 px | 1.15 | -0.01em | none |
| H2 | Playfair Display | 700 | 32 / 25 px | 1.2 | -0.005em | none |
| H3 | Playfair Display | 600 | 24 / 20 px | 1.3 | 0 | none |
| H4 | Montserrat | 600 | 19 px | 1.4 | +0.01em | none |
| H5 | Montserrat | 600 | 15 px | 1.4 | +0.06em | UPPERCASE |
| H6 | Montserrat | 600 | 13 px | 1.4 | +0.09em | UPPERCASE (color slot 1) |

The H4→H6 switch to the sans is deliberate: small headings in Montserrat caps create an editorial "label" rhythm that echoes the pin overlays.

**Buttons:** Montserrat · 600 · 15px · UPPERCASE · letter-spacing +0.05em.

**Content width (readability):** Customize → **Single Posts → Content Width = Narrow**, max **collapse to ~50rem (800px)**. Long-form reads better in one comfortable column.

---

## 3. Header
**Customize → Header.**
- Layout: **logo left, primary navigation right.** Mobile: hamburger right.
- Background: slot 8 cream `#F5EBDD`. Bottom border: 1px slot 6 `#E4D6BF`.
- **Sticky:** main row sticky on scroll (light, no shrink-to-nothing).
- **Site title** (until you have a logo image): Customize → Site Identity → keep text title "Bloom & Lantern". Style via Header → Site Title typography: Playfair Display 700, ~26px, color slot 3. Hide the tagline in the header.
- Nav links: Montserrat 500, 15px, color slot 4; **hover/active = slot 1 terracotta** (amber underline added in §8).
- Optional: add the Search toggle to the header.
- **Favicon:** Site Identity → Site Icon → a simple lantern or leaf mark, 512×512 (make in Canva).

---

## 4. Footer (the signature)
**Customize → Footer.**
- **Background: slot 9 dusk blue `#2C3E50`.** This is the brand signature — a warm "evening" close to the cream body.
- Footer widget area: **3 columns** + a bottom bar.
  - Col 1: brand wordmark (cream) + one-line blurb: *"Small-space balcony & patio styling, decor, and container gardening."*
  - Col 2: **Explore** — links to Balcony Ideas + Patio Ideas categories.
  - Col 3: **Site** — About · Contact · Privacy Policy · Affiliate Disclosure.
- Text color: cream `#F5EBDD`. Link hover: **amber `#E8B86D`**.
- Widget/column headings: Montserrat 600 UPPERCASE, **amber `#E8B86D`** (styled in §8).
- Bottom bar: "© Bloom & Lantern" + footer menu, muted cream, smaller.

---

## 5. Buttons
**Customize → General → Buttons (Global).**
- **Primary:** background slot 1 `#C97B5A` · text `#FFF8EF` (warm cream) · radius **6px** · padding **14px 28px** · Montserrat 600 uppercase.
- **Hover:** background slot 2 `#A85F42` + the **amber glow** (CSS §8).
- **Outline/secondary** (use Kadence's "outline" style where offered): transparent bg, slot 1 border + text, hover fills slot 1.

---

## 6. Blog & single-post layout
- **Single Posts:** no sidebar (or right sidebar only for email signup); content `#FFFDF8` boxed on the cream page for a subtle editorial lift (Customize → Single → Content Background = `#FFFDF8`, add a soft shadow). Featured image large at top. Post meta minimal: category + date in Montserrat caps, slot 5.
- **Archive/Blog:** card grid, 2–3 columns, each card slot 7 `#EFE3D1` background with slot 6 border; show featured image + title (Playfair) + category eyebrow.
- **Permalinks** already set to Post name. Assign every post to **Balcony Ideas** or **Patio Ideas**.

---

## 7. Homepage (phase 2, after a few posts are live)
Set a **static homepage** (Settings → Reading → A static page). Build with Kadence blocks:
1. **Hero** (cream): Playfair H1 "Make the most of your small balcony or patio", Montserrat subhead, two buttons → the Balcony hub + Patio hub. Optional warm hero photo with a lower-third cream band (mirrors the Aesthetic Hero pin).
2. **Two category cards** — Balcony (honey tint) + Patio (sage tint), each linking to its hub.
3. **Latest guides** grid.
4. **Email signup band** (sage or dusk background) — start collecting subscribers early.

---

## 8. Additional CSS (the polish + signature)
**Customize → Additional CSS.** Paste as-is. Uses Kadence palette vars + brand extras; selectors scoped to avoid fighting the theme.

```css
/* ===== Bloom & Lantern — Golden Hour polish ===== */
:root{
  --bl-terracotta:#C97B5A; --bl-terracotta-dark:#A85F42;
  --bl-sage:#9CAF88; --bl-honey:#C8A06A; --bl-amber:#E8B86D;
  --bl-dusk:#2C3E50; --bl-cream:#F5EBDD;
}

/* Warm amber text selection */
::selection{ background:rgba(232,184,109,.40); color:#2E2B27; }

/* Buttons: lantern glow on hover */
.wp-block-button__link,.button,button.kb-button,input[type="submit"]{
  transition:background-color .2s ease, box-shadow .25s ease, transform .15s ease;
}
.wp-block-button__link:hover,.button:hover,button.kb-button:hover,input[type="submit"]:hover{
  box-shadow:0 6px 22px -6px rgba(201,123,90,.65), 0 0 0 3px rgba(232,184,109,.30);
  transform:translateY(-1px);
}

/* Body links: terracotta with a soft underline that warms to amber */
.entry-content a:not(.wp-block-button__link):not(.button){
  color:var(--bl-terracotta-dark); text-decoration:underline;
  text-decoration-color:rgba(201,123,90,.45);
  text-underline-offset:3px; text-decoration-thickness:1.5px;
  transition:color .2s ease, text-decoration-color .2s ease;
}
.entry-content a:not(.wp-block-button__link):not(.button):hover{
  color:var(--bl-terracotta); text-decoration-color:var(--bl-amber);
}

/* Eyebrow / label utility (apply class to a paragraph) */
.eyebrow{ font-family:"Montserrat",sans-serif; text-transform:uppercase;
  letter-spacing:.12em; font-size:.78rem; font-weight:600; color:var(--bl-terracotta-dark); }

/* Editorial drop cap on the first paragraph of a post (remove this block if not wanted) */
.single .entry-content > p:first-of-type::first-letter{
  font-family:"Playfair Display",serif; font-weight:700; font-size:3.2em;
  line-height:.8; float:left; margin:.05em .12em 0 0; color:var(--bl-terracotta); }

/* Blockquote + affiliate disclosure: warm card, terracotta edge */
.entry-content blockquote{
  background:#FBF1E2; border-left:4px solid var(--bl-terracotta);
  border-radius:0 8px 8px 0; padding:1rem 1.25rem; font-style:normal; color:#4A463F; }

/* Comparison tables: sage header, honey hairlines */
.entry-content table thead th{ background:var(--bl-sage); color:#23291E;
  font-family:"Montserrat",sans-serif; letter-spacing:.02em; }
.entry-content table td,.entry-content table th{ border-color:var(--bl-honey); }

/* Footer widget headings = amber caps */
.site-footer .widget-title,.site-footer .wp-block-heading{
  color:var(--bl-amber); text-transform:uppercase; letter-spacing:.08em;
  font-family:"Montserrat",sans-serif; font-size:.9rem; }
```

> If the drop cap lands somewhere you don't want, delete that one block. If footer headings don't pick up the color, the widget-title selector may differ by Kadence version — tell me and I'll adjust it.

---

## 9. Accessibility & quality floor
- Body charcoal on cream and cream on dusk both clear WCAG AA. Keep terracotta for accents/large text, not small body text on cream.
- Don't remove focus outlines; Kadence keyboard focus is on by default.
- The glow/underline transitions are subtle and respect `prefers-reduced-motion` (they're hover-only, no autoplay).

---

## Apply order (fastest path)
1. Fonts local (§0) → 2. Palette (§1) → 3. Typography (§2) → 4. Header (§3) → 5. Footer (§4) → 6. Buttons (§5) → 7. Blog/Single layout (§6) → 8. Paste Additional CSS (§8). Homepage (§7) after a few posts are published.
