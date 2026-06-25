# Guideline: Pinterest Pin Spec

How the pinterest-strategist builds a pin batch for a post. Obeys `guardrails/pinterest-policy.md`.

## Design spec (every pin)
- **Size:** 1000×1500 px, **2:3** vertical. No exceptions.
- **Text overlay:** bold, high-contrast, legible at thumbnail size; 4–8 words of hook; brand mark small.
- **Image:** original photo preferred (`[YOUR PHOTO]` from the post) > free stock (Pexels/Unsplash, license-safe).
- **Consistency:** recognizable template family (fonts/colors) so the account reads as one authority.

## The angle taxonomy (generate multiple FRESH designs per post)
Each post spawns several pins, each a different angle → different design + title (not a re-share):
| Angle | Hook framing | Example title |
|---|---|---|
| Search | matches the literal query | "Best Balcony Vegetables for Beginners" |
| Curiosity | gap/intrigue | "The Veggies That Thrive in Tiny Pots (Most People Skip #3)" |
| Product | gear/solution | "7 Must-Have Tools for a Balcony Veggie Garden" |
| Budget | cheap/frugal | "Grow a Balcony Garden for Under the Cost of One Restaurant Meal" |
| Beginner | reassurance | "Balcony Gardening for Total Beginners: Start Here" |
| Seasonal | time-bound | "What to Plant on Your Balcony This Spring" |
| List/Number | listicle pull | "10 Easy Vegetables for Small Balconies" |

Default batch: **4–6 pins** per new post across distinct angles.

## Copy per pin
- **Pin title:** keyword-rich, ≤ ~100 chars, matches the overlay intent. Front-load the keyword.
- **Pin description:** 2–4 natural sentences with primary + secondary keywords and a soft CTA
  ("Save this for your spring planting list"). Vary descriptions across pins — never copy-paste.
- **Board:** assign to the keyword-named board for the post's pillar/sub-topic.
- **Suggested image filename:** keyword-based, hyphenated.
- **Destination URL:** the blog post (token `{{DOMAIN}}/<slug>`), not a raw affiliate link.

## Schedule
- Spread the batch over days (e.g., 1 pin/day), not all at once.
- Suggest publish slots in the audience-evening window; spaced; mark each in the tracker.

## Output = filled `templates/pin-batch.md`
One row per pin: angle, overlay text, design brief (layout/colors/image direction), title, description,
board, filename, destination, scheduled date, Pin Batch ID.
