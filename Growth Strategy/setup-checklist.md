# Site Setup Checklist — Milestone 1 "Site Ready"

> Goal: a live, trustworthy WordPress site + Pinterest presence ready for affiliate/ad approval, on a bootstrap budget.
> Brand: **Bloom & Lantern** · Domain: **https://bloomandlantern.com** · Host: **Namecheap Stellar Plus** (cPanel + LiteSpeed).
> Status legend: `[x]` done · `[~]` drafted/partial · `[ ]` not started · **(owner)** = you do it, I cannot log in.

---

## A. WordPress / tech stack  **(owner executes; I prepared the content)**

- [x] Domain `bloomandlantern.com` purchased (Namecheap, 2026-06-27)
- [x] Hosting purchased — Stellar Plus (Namecheap, 2026-06-27)
- [ ] **Point domain at hosting (owner)** — bought together, so Namecheap usually auto-links. Verify in Namecheap → Domain List → the domain's nameservers match the hosting (or the hosting shows the domain as primary). Allow DNS to propagate.
- [ ] **Install WordPress (owner)** — Namecheap dashboard → Hosting List → **Manage → cPanel** → **Softaculous / "Install WordPress"**:
  - Protocol: **https://** · Domain: `bloomandlantern.com` · Directory: **leave blank** (install at root)
  - Site name: **Bloom & Lantern** · Tagline: *Small-space balcony & patio styling* (editable later)
  - Admin user: NOT "admin" — pick a custom username + a strong password (save it)
- [ ] **Enable free SSL (owner)** — cPanel → SSL/TLS Status → run **AutoSSL** for the domain. Confirm `https://` loads with a padlock before going live.
- [ ] **Force HTTPS + www decision (owner)** — pick non-www `https://bloomandlantern.com` (matches our links). Set in WP → Settings → General (both Site Address + WordPress Address). LiteSpeed Cache can force HTTPS.
- [ ] **Permalinks (owner)** — WP → Settings → Permalinks → **Post name** (`/%postname%/`).
- [ ] **Delete sample content (owner)** — remove the "Hello World" post + "Sample Page"; set a real default category (below) and delete "Uncategorized".
- [ ] **Theme (owner)** — Appearance → Themes → Add New → install **Kadence** *or* **GeneratePress** (both free, fast) → Activate. (Speed = SEO + future ad RPM.)
- [ ] **Plugins (free) (owner)** — Plugins → Add New:
  - **Rank Math SEO** (titles, meta, schema, sitemap, Open Graph for Rich Pins)
  - **LiteSpeed Cache** — Stellar runs LiteSpeed, so this is the right caching plugin; it also does **image optimization** (via free QUIC.cloud) so you may not need a separate image plugin
  - *(optional)* a **Table of Contents** plugin if your theme/Rank Math block doesn't cover it (e.g. SimpleTOC or LuckyWP)
- [ ] **Categories = pillars (owner)** — create two top-level categories: **Balcony Ideas** and **Patio Ideas**. (Sub-categories optional later: Privacy, Gardening, Furniture, Budget, Renter.) Set one as the default; delete "Uncategorized".
- [ ] **Menus (owner)** — Primary nav: Home · Balcony Ideas · Patio Ideas · About. Footer menu: About · Contact · Privacy Policy · Affiliate Disclosure.

---

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

### Launch board taxonomy (start with these ~10, keyword-named)

> Pinterest favors focused, keyword-named boards. These 10 cover both spaces and receive the already-designed pin batches (PB-001 → PB-009). Add more granular boards (e.g. "Patio Furniture Materials", "Small Balcony Makeovers") as volume grows, or map those pins to the closest board below.

**Balcony space**
1. **Small Balcony Ideas** — *Small balcony ideas for apartments and tiny outdoor spaces: seating, layout, decor, and styling to make the most of a narrow balcony.*
2. **Cozy Balcony Decor** — *Cozy balcony decor ideas: warm string lights, soft textiles, plants, and seating to turn a small balcony into a relaxing retreat.*
3. **Budget Balcony Ideas** — *Budget balcony ideas and cheap small balcony upgrades: affordable rugs, lighting, and decor that look expensive for less effort.*
4. **Apartment & Renter Balcony Ideas** — *Renter-friendly, no-drill balcony decorating ideas for apartments: removable, deposit-safe ways to style a rental balcony.*
5. **Balcony Privacy Ideas** — *Balcony privacy ideas: screens, curtains, plants, and no-drill ways to feel hidden on an apartment balcony.*
6. **Balcony Garden & Container Planters** — *Balcony container gardening and self-watering planters: small-space, low-maintenance ways to grow herbs, veg, and flowers on a balcony.*

**Patio space**
7. **Small Patio Ideas** — *Small patio ideas to style a tiny outdoor space: seating, flooring, plants, lighting, and privacy for apartment and townhouse patios.*
8. **Patio Furniture Ideas** — *Patio furniture ideas for small spaces: compact seating, bistro sets, sectionals, and space-saving outdoor furniture that actually fits.*
9. **Patio Garden Ideas** — *Patio garden ideas for small spaces: container gardens, vertical planters, edibles, and flowers to turn a bare patio into a lush garden.*
10. **Patio Privacy & Decor** — *Patio privacy ideas and small patio decor: screens, plants, and styling to make a small patio private, cozy, and finished.*

*(Optional 11th: a brand board "Bloom & Lantern | Best Of" to repin your top performers.)*

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
- [ ] Pinterest business account + website claimed + Rich Pins on + the 10 launch boards created

**Next:** publish the content base and start scheduling the pin batches (Milestone 2).
