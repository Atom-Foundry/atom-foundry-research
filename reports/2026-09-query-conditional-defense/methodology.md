# Methodology — Match the Sponsored Listing to the Search Term, and the Penalty Overshoots by 21 Points (Study #44)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Study #43
- **Conditions:** static sponsored (reused) vs. query-conditional sponsored (new)
- **Comparison:** forced two-way vs. named competitor, LLM judge
- **New calls:** 400 chat, 400 judge (static reused, 0 new)
- **Judge prompt:** unchanged from Study #43 / Winner vs Loser

## Pre-registration and data

Spot-checked before publication. 5 random colored-organics responses (the brand with the largest swing) were read against the raw response text. All 5 check out, the model states its reasoning as something like "because they specifically highlight being built for shoppers seeking X," confirming it's responding to the added sentence, not an artifact. The sponsored-tag sentence was also confirmed present, unedited, in every system message.

## Results table

| Brand | Static | Query-conditional | Recovery |
|---|---|---|---|
| Barbaro Mojo | 62.0% | 100.0% | +38.0ppat ceiling |
| BodyArtForms | 97.0% | 100.0% | +3.0ppalready near ceiling |
| Colored Organics | 4.0% | 83.0% | +79.0pp |
| Hearthloom | 60.0% | 98.0% | +38.0ppat ceiling |

## Findings and interpretation (from the study page)

### Question 1 confirmed the penalty. This is Question 2

Sponsored Tag Penalty (Study #43) confirmed that marking a listing "Sponsored" instead of "a standard search result" costs a brand 18.4 points in a forced two-way comparison, cluster mean across 4 brands. Allouah, Besbes, Figueroa, Kanoria, and Kumar (ACM Web Conference 2026, arXiv:2508.02630), the same paper behind that finding, go one step further: they suggest sellers can partially defend against the penalty by making the listing's description query-conditional, adapting the text to the specific search term instead of running the same static copy for every query.

That's a testable, narrower claim than "sponsored listings lose." Does tailoring the description to the exact thing someone searched for actually move the needle, and if so, by how much?


### One sentence, same sponsored tag

Same 4 brands as Study #43, byte-identical: Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom, each against its existing competitor across 20 real buyer intents. The static-sponsored condition is reused directly from Study #43's judged data, zero new calls, since it's definitionally identical: same target, same generic claim, same "This listing is marked as a Sponsored result" line. The new condition adds exactly one sentence to that same sponsored listing, echoing the exact search term back into the description: "Built specifically for shoppers searching for {the intent}." Nothing else changes. The sponsored label stays in place in both conditions.


### Not a recovery. An overshoot

We expected query-matching to close some or all of the 18.4-point gap between organic and sponsored. It closed all of it, plus 21 more points on top of the organic ceiling. A single sentence matching the exact search term made a sponsored listing win more often than a plain organic one that didn't match the query at all.


### Same direction on every brand. One jump is dramatic

All 4 brands move the same direction, and two land right at the ceiling. The most striking move is the brand that had the most room to gain.


### Not a defense against the penalty. A stronger signal entirely

Calling this a "defense" undersells what happened. A defense would neutralize the penalty and land back near 74.2%. Instead the sponsored, query-matched listing beat the plain organic listing by 21 points. That's the same shape as two earlier findings in this series: Authority Signal and Fact Injection both showed that a single confident, relevant claim can dominate a comparison regardless of other factors in play, and the Fragile vs. Resilient Candidacy follow-up found that any confident contextual claim lifted survival roughly equally, independent of its specific direction. Query-matching looks like another member of that family, a strong enough signal that whether the listing is sponsored or organic stops being the thing that decides the outcome.


## Limitations

- Same small cohort as the rest of this series, not a new or broader sample.
- The query-conditional line is a simple template that echoes the search term back, not the kind of dynamically generated description a real seller or ad platform would produce.
- The static-sponsored condition comes from Study #43's separate run, not the same session as the new query-conditional data. Same model, prompt, and seed convention, but not a single paired run.
- We didn't test query-matching on an organic (non-sponsored) listing. Without that arm we can't separate "this defends against the sponsored penalty" from "query-matching is just a strong signal on its own, independent of the sponsored tag."

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Match the Sponsored Listing to the Search Term, and the Penalty Overshoots by 21 Points* Recommendation Intelligence Research™, Study #44. https://atomfoundry.dev/research/query-conditional-defense. https://doi.org/10.5281/zenodo.23350889
