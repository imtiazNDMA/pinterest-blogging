---
type: strategy
updated: 2026-06-26
---

# 🗺️ Site Structure

← [[Home]] · [[WordPress Categories & Tags]] · [[Content Pillars]]

How the WordPress site is organized so Google reads topical authority and readers navigate easily. The model is
**silos**: pillar (hub) page → supporting posts, all interlinked.

## URL + silo model
```
{{DOMAIN}}/
├── /  (homepage — featured pillars + latest)
├── /small-balcony-ideas/            ← Pillar 1 hub page
│     ├── /cozy-small-balcony-ideas/
│     ├── /small-balcony-ideas-on-a-budget/
│     ├── /renter-friendly-balcony-ideas/
│     ├── /small-balcony-makeover-before-and-after/
│     └── /balcony-privacy-ideas-for-apartments/  (next)
├── /balcony-furniture/              ← Pillar 2 hub (future)
├── /balcony-privacy/                ← Pillar 3 hub (future)
├── /balcony-garden/                 ← Pillar 4 hub (future)
├── /balcony-lighting/ , /balcony-flooring/  (future)
│
├── /small-patio-ideas/              ← Patio Pillar 1 hub (future)
│     ├── /small-patio-decorating-ideas/
│     ├── /cozy-patio-ideas-small-spaces/
│     ├── /modern-patio-design/
│     └── /small-covered-patio-ideas/
├── /patio-garden-ideas/             ← Patio Pillar 2 hub (future)
├── /patio-furniture-ideas/          ← Patio Pillar 3 hub — money (future)
└── /patio-privacy-ideas/            ← Patio Pillar 4 hub (future)
```
Use a **flat URL** (`/post-slug/`), not `/category/post/` — cleaner, avoids broken links if a post changes category.

## Required pages (trust + legal — needed before ads/affiliates)
- [ ] **About** — who's behind the blog (E-E-A-T; can be a brand persona, honest)
- [ ] **Contact**
- [ ] **Privacy Policy** (required — cookies, analytics, ads)
- [ ] **Affiliate Disclosure** (required — FTC; linked from every monetized post)
- [ ] **Terms of Use / Disclaimer**
- [ ] **Start Here** (optional — routes new readers into pillars)

## Navigation
- **Top menu:** Home · the 4–6 pillar hubs · About · (Start Here)
- **Footer:** About · Contact · Privacy · Affiliate Disclosure · Terms
- **In-post:** breadcrumb to pillar; 3+ internal links; related-posts at the end.

## Tech stack (bootstrap)
- WordPress (self-hosted) + a fast, lightweight theme (e.g., Kadence/GeneratePress free).
- Plugins: SEO (Rank Math/Yoast free), caching, image optimization, a table-of-contents.
- Analytics: Google Analytics 4 + Google Search Console (verify both at launch).

## Launch checklist → [[Weekly Routine & SOPs]]
