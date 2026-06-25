# Playbook: Niche Validation

Used by the **niche-strategist** agent / `/niche-research`. Goal: commit to a niche with evidence, not vibes.

## Niche criteria (a good niche scores high on all)
- **Pinterest visual demand** — people search & save it on Pinterest (visual, idea-driven topics).
- **Evergreen search depth** — many year-round informational queries (not one-off news).
- **Amazon + affiliate product intent** — natural, ideally repeat-purchase products.
- **Ad-friendly informational volume** — enough how-to/guide content for display-ad RPM.
- **Beatable competition** — SERPs not fully owned by giant authority sites; room for a small blog.
- **Cluster-expansion room** — can grow from a narrow entry into a broad vision.
- **Low seasonality risk** — year-round demand, or a plan to smooth the off-season.

## Steps
1. List candidates from the user's passions (gardening, decor/organization, crafts/DIY, pets) + leading candidate.
2. For each, gather signals (WebSearch/WebFetch): autocomplete breadth, who ranks, product availability, seasonality.
3. Score 1–5 per criterion in `templates/niche-scorecard.md`; weight demand + monetization highest; total it.
4. Write a scorecard per candidate + a comparison file; recommend one with rationale + expansion path.
5. **Validation gate:** label estimates `(est — needs validation)`; tell the user which exports (Keyword
   Planner, Pinterest Trends) would confirm before heavy investment.

## Decision
Commit when the top niche clearly wins on demand + monetization + rankability and fits the user's knowledge.
On commit: update `.claude/CLAUDE.md` + `.claude/memory.md`, define the 4 content pillars, go to keyword research.
