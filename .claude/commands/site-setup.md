---
description: Walk through WordPress + Pinterest + trust-page setup using the site-setup playbook.
argument-hint: "[optional: step, e.g. 'trust pages' or 'pinterest']"
---

Guide the site setup. Scope: `$ARGUMENTS` (empty = full checklist).

Follow `.claude/playbooks/site-setup.md` step by step. For the requested scope:
1. Show the checklist items with status (ask the user what's done).
2. For trust pages (About / Contact / Privacy Policy / Affiliate Disclosure), generate ready-to-paste
   Markdown drafts into `Content/pages/` using the compliant disclosure text from
   `.claude/guardrails/affiliate-compliance.md` (with `Bloom & Lantern`/`https://bloomandlantern.com` tokens).
3. For Pinterest, walk through business account, website claim, Rich Pins, and the initial keyword-named
   boards (one per pillar) — board names + descriptions drafted for them.
4. For WordPress/tech, give the bootstrap stack (host, free fast theme, free plugins) from `.claude/memory.md`
   and a concrete action order.

Keep it to concrete next actions, not theory. Track completion in `Growth Strategy/setup-checklist.md`.
