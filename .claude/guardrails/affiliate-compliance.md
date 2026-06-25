# Guardrail: Affiliate & Ad Compliance (FTC + Amazon Associates)

**Status: hard rules. Violating these can get the Amazon account terminated or the site de-monetized.**
Re-verify specifics before relying — programs change. Sources tracked in `.claude/memory.md`.

## FTC disclosure (US)
- Every post containing affiliate links MUST include a **clear, conspicuous disclosure ABOVE the first
  affiliate link** — not buried in a footer, not only on a separate page.
- Use plain language a reader understands. Default line (adjust to brand voice, keep it clear):
  > *"This post contains affiliate links. If you buy through them, {{BLOG_NAME}} may earn a small
  > commission at no extra cost to you."*
- A site-wide **Affiliate Disclosure page** is required in addition to the per-post line.
- Disclosures apply to Pinterest too: if a **pin links directly** to an affiliate URL or the pin itself is
  materially an ad, it must be disclosed (`#ad`/"affiliate"). Prefer linking pins to blog posts, not raw affiliate links.

## Amazon Associates ToS (the easy-to-break ones)
- **NEVER state prices, "$X", "only $Y", "cheapest", "on sale", discount %, or stock/availability.**
  Prices change and caching them violates the Operating Agreement. Describe value qualitatively
  ("budget-friendly," "a splurge that lasts," "great value for the size") — never a number.
- **NEVER scrape or copy Amazon review text, star ratings, or "X bought in past month" data.**
- **Required Associate disclosure** somewhere obvious (commonly): *"As an Amazon Associate {{BLOG_NAME}}
  earns from qualifying purchases."* Put on disclosure page + near Amazon links.
- **No link cloaking that hides it's Amazon**, no affiliate links in email/PDF/offline, no incentivized clicks
  ("click my link to support me" framing is risky — keep it about helping the reader).
- **3 qualified sales within 180 days** are required to keep the account after applying (personal orders don't count).
- Use the official `{{AMAZON_TAG}}` tracking ID on every Amazon link once approved.

## Other affiliate programs (seed/planter/tool brands, ~5–15%)
- Follow each program's own disclosure + linking terms. Same FTC rule applies.
- Prefer higher-rate garden programs for the actual product picks where quality is equal; Amazon is the
  breadth/convenience fallback (24h cart attribution still earns on anything they buy).

## Ad networks (readiness, not yet live)
- **AdSense:** needs original useful content, trust pages (About/Contact/Privacy/Disclosure), clean nav, no thin/copied content.
- **Mediavine Journey:** ~1,000 sessions/mo, requires the Grow plugin, 70% rev share.
- **Raptive:** ~25,000 pageviews/mo (25k–99k band needs 50% tier-1 traffic: US/UK/CA/AU/NZ).
- Ads + affiliate links may coexist but don't let ad density wreck UX (Mediavine/Raptive judge reader experience).

## The disclosure checklist (editor-qa enforces)
- [ ] Per-post FTC line present **above** first affiliate link
- [ ] No prices / "cheapest" / stock claims anywhere
- [ ] No copied Amazon review or rating content
- [ ] Amazon Associate statement present where required
- [ ] Affiliate links are genuinely helpful, not stuffed
