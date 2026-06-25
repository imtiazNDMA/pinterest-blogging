# Playbook: Site Setup (Milestone 1 — "Site Ready")

Goal: a live, trustworthy WordPress site + Pinterest presence ready for affiliate/ad approval. Bootstrap (<$30/mo).

## A. WordPress / tech stack
1. **Domain** (~$10/yr) — short, brandable, niche-hinting. Set `{{DOMAIN}}`.
2. **Hosting** — budget managed WordPress host (~$3–7/mo intro). Self-hosted WordPress.org (NOT wordpress.com).
3. **Theme** — free, fast: Kadence or GeneratePress (free). Speed = SEO + ad RPM.
4. **Plugins (free):** Rank Math (SEO), a caching plugin, image optimization, a table-of-contents plugin.
5. **Analytics:** GA4 + connect Google Search Console (verify the domain).
6. **Permalinks:** post name (`/%postname%/`). Categories = the 4 pillars.

## B. Trust pages (required for Amazon + AdSense)
Generate Markdown drafts in `Content/pages/`:
- **About** — who the site helps + why to trust it (real, specific).
- **Contact** — a form or email.
- **Privacy Policy** — covers cookies, analytics, affiliate tracking, ad networks.
- **Affiliate Disclosure** — FTC + the Amazon Associate statement (from `guardrails/affiliate-compliance.md`).
Link all four in the footer.

## C. Pinterest
1. **Business account** (free). 2. **Claim the website** (verify domain). 3. **Enable Rich Pins.**
4. Create **5–8 keyword-named boards** — one per pillar + key sub-topics; keyword-rich board descriptions.
5. Profile: keyword-rich name + bio aligned to the niche entity (topical authority).

## D. Definition of done (Milestone 1)
- [ ] Site live on `{{DOMAIN}}`, fast theme, clean nav, pillar categories
- [ ] All 4 trust pages published + linked in footer
- [ ] GA4 + Search Console connected
- [ ] Pinterest business account + website claimed + Rich Pins on + first boards created

Track progress in `Growth Strategy/setup-checklist.md`. Next: build the content base (Milestone 2).
