# Site Setup Checklist — Milestone 1 "Site Ready"

> Goal: a live, trustworthy WordPress site + Pinterest presence ready for affiliate/ad approval, on a bootstrap budget.
> Brand: **Bloom & Lantern** · Domain: **https://bloomandlantern.com** · Host: **Namecheap Stellar Plus** (cPanel + LiteSpeed).
> Status legend: `[x]` done · `[~]` drafted/partial · `[ ]` not started · **(owner)** = you do it, I cannot log in.

---

## A. WordPress / tech stack  **(owner executes; I prepared the content)**

- [x] Domain `bloomandlantern.com` purchased (Namecheap, 2026-06-27)
- [x] Hosting purchased — Stellar Plus (Namecheap, 2026-06-27)
- [x] **Point domain at hosting (owner)** — bought together, so Namecheap usually auto-links. Verify in Namecheap → Domain List → the domain's nameservers match the hosting (or the hosting shows the domain as primary). Allow DNS to propagate.
- [x] **Install WordPress (owner)** — Namecheap dashboard → Hosting List → **Manage → cPanel** → **Softaculous / "Install WordPress"**:
  - Protocol: **https://** · Domain: `bloomandlantern.com` · Directory: **leave blank** (install at root)
  - Site name: **Bloom & Lantern** · Tagline: *Small-space balcony & patio styling* (editable later)
  - Admin user: NOT "admin" — pick a custom username + a strong password (save it)
- [ ] **Enable free SSL (owner)** — cPanel → SSL/TLS Status → run **AutoSSL** for the domain. Confirm `https://` loads with a padlock before going live.
- [ ] **Force HTTPS + www decision (owner)** — pick non-www `https://bloomandlantern.com` (matches our links). Set in WP → Settings → General (both Site Address + WordPress Address). LiteSpeed Cache can force HTTPS.
- [ ] **Permalinks (owner)** — WP → Settings → Permalinks → **Post name** (`/%postname%/`).
- [x] **Delete sample content (owner)** — remove the "Hello World" post + "Sample Page"; set a real default category (below) and delete "Uncategorized".
- [x] **Theme (owner)** — **Kadence** installed + activated (2026-06-27).
- [ ] **Customize Kadence (owner)** — apply the full "Golden Hour" brand spec in `Growth Strategy/kadence-theme-spec.md`: palette, Playfair × Montserrat typography, dusk-blue footer, amber-glow buttons, Additional CSS. Matches the pin design system.
- [ ] **Plugins (free) (owner)** — Plugins → Add New:
  - **Rank Math SEO** (titles, meta, schema, sitemap, Open Graph for Rich Pins)
  - **LiteSpeed Cache** — Stellar runs LiteSpeed, so this is the right caching plugin; it also does **image optimization** (via free QUIC.cloud) so you may not need a separate image plugin
  - *(optional)* a **Table of Contents** plugin if your theme/Rank Math block doesn't cover it (e.g. SimpleTOC or LuckyWP)
- [ ] **Categories = pillars (owner)** — create two top-level categories: **Balcony Ideas** and **Patio Ideas**. (Sub-categories optional later: Privacy, Gardening, Furniture, Budget, Renter.) Set one as the default; delete "Uncategorized".
- [ ] **Menus (owner)** — Primary nav: Home · Balcony Ideas · Patio Ideas · About. Footer menu: About · Contact · Privacy Policy · Affiliate Disclosure.

---

## A2. WordPress MCP (lets Claude publish content) — security notes
- Config lives in `.mcp.json` (Automattic `@automattic/mcp-wordpress-remote`, **version-pinned to `0.3.5`** — bump deliberately after reviewing release notes, never auto-`@latest`, so a compromised future release can't run with your site credentials).
- **Credentials are NOT in the repo** — `.mcp.json` references `${WP_API_USERNAME}` / `${WP_APP_PASSWORD}` env vars you set locally.
- **Scope the Application Password to least privilege:** create it on a **dedicated low-privilege WP user** (Editor/Author is plenty for publishing posts/pages), not your main admin with `manage_options`/`edit_plugins`. If you already generated one on the admin account, **rotate it** (Users → Profile → revoke + regenerate on the limited user).
- Requires the `wordpress-mcp` plugin installed + enabled on the site, Node.js locally, and a Claude Code restart to load. (Steps in the chat history.)

## B. Trust pages  (required for Amazon + AdSense)

Drafts live in `Content/pages/` — paste each into a WordPress **Page**, fill the placeholders, publish, link all four in the footer.

- [~] **About** — `Content/pages/about.md` (drafted; review/personalize before publish)
- [x] **Contact** — `Content/pages/contact.md` (drafted 2026-06-27)
- [~] **Privacy Policy** — `Content/pages/privacy-policy.md` (drafted; **run through Termly or iubenda** to confirm it matches your final analytics/ad stack, then paste)
- [~] **Affiliate Disclosure** — `Content/pages/affiliate-disclosure.md` (drafted; FTC + Amazon Associate language compliant)

**Placeholders to fill before publishing any page (owner):**
- `{{CONTACT_EMAIL}}` → your real contact address (consider a branded one: hello@bloomandlantern.com via cPanel email)
- `[OWNER: add launch date]` → the publish date on each page

---

## C. Pinterest  **(owner executes)**

- [ ] **Business account (free)** — create at pinterest.com/business/create (or convert a personal account).
- [ ] **Profile** — Name: **Bloom & Lantern | Small Balcony & Patio Ideas** · Bio (keyword-rich): *"Small-space balcony and patio styling, decor, and container gardening. Cozy, renter-friendly ideas for tiny outdoor spaces."* · profile photo/logo · set website to `https://bloomandlantern.com`.
- [ ] **Claim the website** — Settings → Claimed accounts → Claim `bloomandlantern.com` (add the meta tag to the WP `<head>` via Rank Math, or upload the HTML file, or add the DNS TXT in Namecheap). Claiming enables analytics + your logo on every pin.
- [ ] **Enable Rich Pins** — Rank Math outputs the Open Graph tags Rich Pins need; validate one live post URL in the Pinterest Rich Pins Validator to switch them on account-wide.
- [ ] **Create the launch boards** (below) with keyword-rich descriptions.

### Board taxonomy — ONE BOARD PER PILLAR (revised 2026-06-27)

> **Model: board = a content pillar (broad head keyword); the pins inside it carry the focused long-tail
> keywords.** A well-fed pillar board is a strong Pinterest relevance signal, and our pillars already are the
> topic clusters. 12 pillar boards (6 balcony + 6 patio). **Launch only the boards that have content** (an
> empty board hurts you); add the ⏳ ones when their pillar gets posts. Use board **sections** for the focused
> angles inside a pillar (e.g. Small Balcony Ideas → Cozy / Boho / Budget / Modern / Makeovers).

**Balcony space**
1. **Small Balcony Ideas** *(Decor & Styling pillar)* — *Small balcony ideas for apartments and tiny outdoor spaces: cozy, modern, boho, budget, renter, and makeover decor and styling.* ✅ feeds: small-balcony-patio-ideas (hub), cozy, budget, renter, apartment-decorating, makeover, modern, aesthetic, boho. Sections: Cozy · Boho & Aesthetic · Budget · Modern · Renter/Apartment · Makeovers.
2. **Balcony Furniture Ideas** *(Furniture & Seating pillar)* — *Balcony furniture and seating ideas for small spaces: bistro sets, swing chairs, benches, and space-saving outdoor seating.* ⏳ pillar open (no posts yet).
3. **Balcony Privacy Ideas** *(Privacy & Shade pillar)* — *Balcony privacy ideas: screens, curtains, plants, and no-drill ways to feel hidden on an apartment balcony.* ✅ feeds: balcony-privacy-ideas-for-apartments.
4. **Balcony Garden Ideas** *(Garden & Plants pillar)* — *Balcony garden ideas and container gardening: best balcony plants, flowers, herbs, and self-watering planters for small spaces.* ✅ feeds: balcony-garden-ideas, best-balcony-plants, small-balcony-garden, apartment-balcony-garden, balcony-flowers, best-self-watering-planters-balcony.
5. **Balcony Flooring Ideas** *(Flooring pillar)* — *Balcony flooring ideas to cover ugly concrete: interlocking deck tiles, outdoor rugs, and renter-friendly floor options.* ✅ feeds: balcony-flooring-ideas.
6. **Balcony Lighting Ideas** *(Lighting pillar)* — *Balcony lighting ideas: warm string and fairy lights, solar and no-outlet options, and cozy ways to light a small balcony.* ✅ feeds: balcony-lighting-ideas.

**Patio space**
7. **Small Patio Ideas** *(Decor & Design pillar)* — *Small patio ideas to style a tiny outdoor space: seating, flooring, plants, lighting, and privacy for apartment and townhouse patios.* ✅ feeds: small-patio-ideas (hub), small-patio-decorating-ideas.
8. **Patio Furniture Ideas** *(Furniture & Seating pillar)* — *Patio furniture ideas for small spaces: compact seating, bistro sets, DIY builds, and space-saving outdoor furniture.* ✅ feeds: patio-furniture-ideas, diy-patio-furniture.
9. **Patio Garden Ideas** *(Garden & Plants pillar)* — *Patio garden ideas for small spaces: container gardens, vertical planters, edibles, and flowers for a lush small patio.* ✅ feeds: patio-garden-ideas, small-patio-garden.
10. **Patio Privacy Ideas** *(Privacy & Shade pillar)* — *Patio privacy ideas: screens, walls, plants, and privacy planters to make a small or ground-level patio feel hidden.* ✅ feeds: patio-privacy-ideas.
11. **Covered Patio Ideas** *(Covered/Structure pillar)* — *Covered patio ideas for small spaces: pergolas, shade, and enclosed patio designs.* ⏳ pillar open (no posts yet).
12. **Patio Flooring Ideas** *(Flooring/Hardscape pillar)* — *Small patio flooring ideas: pavers, concrete, gravel, and brick options compared for a small patio.* ⏳ pillar open (no posts yet).

*(Optional brand board: "Bloom & Lantern | Best Of" to repin your top performers.)*

> **Pin board assignment:** every pin goes to its pillar board first (see the `Pinterest Board` column in the
> tracker, remapped to these 12 names 2026-06-27), then optionally added to one other relevant pillar board a
> few days later. Board carries the broad keyword; the pin carries the focused one.

---

## D. Analytics  **(owner executes)**

- [ ] **GA4** — create a property at analytics.google.com → copy the **Measurement ID** (`G-XXXXXXX`) → add it via Rank Math (or Site Kit) so it loads site-wide.
- [ ] **Google Search Console** — add the property (Domain property via DNS TXT in Namecheap is cleanest, or URL-prefix verified through GA4/Rank Math) → **submit the sitemap** (`https://bloomandlantern.com/sitemap_index.xml`, generated by Rank Math).
- [ ] *(later, when traffic exists)* connect Pinterest Analytics (auto once the site is claimed).

---

## E. Publish + monetization sequencing

**Publish order (owner, after WP is live):**
1. Publish the **4 trust pages** first (footer-linked).
2. Publish the **hub posts** to anchor each space: `small-patio-ideas` (Rec 47) and the balcony pillar `small-balcony-patio-ideas` (Rec 9).
3. Publish the supporting posts and wire internal links (they already point to the right slugs).

**Per-post pre-publish fill (owner):** pick the SEO title (HTML comment atop each draft), fill `[PERSONAL TIP]` + `[YOUR PHOTO]` (real or AI; label AI on Pinterest), confirm category, set featured image.

**Monetization is gated on the site being live (do in this order):**
- [ ] **Amazon Associates** — apply only **after** several posts + trust pages are live. Approval needs real content; you then need **3 qualifying sales within 180 days** to keep the account. Once approved: I do a second find-replace to set `{{AMAZON_TAG}}` and swap every `#affiliate` / `#wayfair-affiliate` placeholder for real tagged links.
- [ ] **Wayfair (or comparable high-AOV furniture/decor program)** — apply for the furniture/planter picks; swap the `#wayfair-affiliate` placeholders once approved.
- [ ] **Ads** — AdSense once content + trust pages are live; **Journey/Raptive** later at their traffic thresholds.

---

## Definition of done (Milestone 1)
- [ ] Site live on `https://bloomandlantern.com`, fast theme, clean nav, Balcony + Patio categories
- [ ] All 4 trust pages published + linked in the footer
- [ ] GA4 + Search Console connected, sitemap submitted
- [ ] Pinterest business account + website claimed + Rich Pins on + the 9 fed pillar boards created (of 12; add the 3 ⏳ when their pillar has posts)

**Next:** publish the content base and start scheduling the pin batches (Milestone 2).
