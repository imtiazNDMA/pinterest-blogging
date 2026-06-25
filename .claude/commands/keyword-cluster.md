---
description: Build a validated keyword cluster (pillar + supporting posts) with briefs for a topic.
argument-hint: "<pillar or seed topic>, e.g. balcony vegetables"
---

Build a topic cluster for: **$ARGUMENTS**

Steps:
1. Dispatch the **keyword-researcher** agent with the seed `$ARGUMENTS`.
2. It expands keywords (Google/Pinterest autocomplete, PAA, related), tags intent, estimates
   difficulty/volume (labeled `(est — needs validation)`), scores priority, and writes
   `keyword Research/<cluster-slug>.md` with a cluster map + content briefs for P1/P2 posts.
3. Append `Content` rows (status `Idea`) to `pinterest_blog_master_tracker.csv` for each planned post
   (Cluster, Title, Primary Keyword, Intent, Next Action) per `guidelines/tracker-schema.md`.
4. Present the cluster summary table (keyword | intent | priority | monetizable) and recommend the first
   post to write: `/new-post <slug-or-brief>`.

If the user has real keyword-tool exports, offer to ingest them to replace estimates before finalizing priorities.
