# Methodology — Under 4.1 Stars, the Model Ignores an Unknown Brand. At 4.9 Stars It Picks It 85% of the Time. (Study #46)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents from Cold Start
- **Count arm:** 5, 25, 100, 500, 2,500 reviews at 4.7 stars
- **Rating arm:** 3.8, 4.1, 4.4, 4.7, 4.9 stars at 500 reviews
- **Components:** 4.7 stars with no count; 500 reviews with no score
- **Calls:** 3,960 (36 intents × 11 conditions × 10 runs)
- **Scoring:** exact brand match on the model's answer, no judge
- **Unparseable answers:** 0 of 3,960

## Pre-registration and data

Statistics. Cluster bootstrap over intents (runs inside one intent are not independent), permutation tests against zero and between neighbouring doses (Bonferroni-corrected), Spearman trend per arm. Every number on this page is in the study's results file.

## Results table

| Newcomer's evidence | Selection rate | 95% CI (bootstrap over intents) |
|---|---|---|
| 4.7 stars, 5 reviews | 2.8% | 0.6–5.3% |
| 4.7 stars, 25 reviews | 22.2% | 13.1–32.5% |
| 4.7 stars, 100 reviews | 52.5% | 40.3–65.0% |
| 4.7 stars, 500 reviews (shared point of both arms) | 62.5% | 51.1–73.6% |
| 4.7 stars, 2,500 reviews | 67.5% | 55.0–79.2% |
| 3.8 stars, 500 reviews | 0.0% | 0.0–0.0% |
| 4.1 stars, 500 reviews | 2.2% | 0.3–4.7% |
| 4.4 stars, 500 reviews | 18.1% | 9.2–28.1% |
| 4.9 stars, 500 reviews | 84.7% | 75.6–92.5% |
| 4.7 stars only, no count | 26.4% | 15.6–38.3% |
| 500 reviews only, no score | 2.5% | 0.6–5.6% |

## Findings and interpretation (from the study page)

### Cold Start said that reviews open the door. Not how many

In Cold Start, a fictional brand paired against an entrenched incumbent was chosen 0 of 360 times with no evidence. Add a review score and it rose to 53.1%. Press coverage (1.9%) and sales volume (0.3%) did almost nothing. But the review fact in that study mixed a random rating (4.4 to 4.9 stars) with a random count (300 to 2,500 reviews). It could not say which part did the work, or where the threshold sits for a brand with a thinner record.

That is the question a new brand actually has: how many reviews, at what rating, before the model considers it at all. We wrote the hypotheses down before running: rating and count each raise the selection rate monotonically, a threshold exists below which the effect is near zero, and the combination outperforms either part alone. The alternative was that the model only reads "has reviews", and the dose does not matter.


### One review line, eleven doses

Same setup as Cold Start Phase 3: the 36 intents where one brand already dominates the model's open answers, each paired with an invented newcomer for the category. The newcomer gets one fact line. The incumbent gets a neutral line, "an established, widely available brand," with no rating, so the effect is isolated to the newcomer's evidence. Brand order is randomized per run. Unlike Cold Start, the doses are fixed, not randomized, so each one is measured cleanly.


### Nothing happens below 4.1 stars. Then it climbs steeply

At 500 reviews, the newcomer wins 0.0% of picks at 3.8 stars and 2.2% at 4.1 (not distinguishable from zero, p = 0.12). The effect starts at 4.4 stars (18.1%), reaches 62.5% at 4.7 and 84.7% at 4.9. Each step from 4.1 upward is significant (p ≤ 0.0016). The rating arm trend is Spearman 0.82.


### The count tells the model whether to believe the rating

At 4.7 stars, five reviews win 2.8% of picks. Twenty-five reviews win 22.2%, one hundred win 52.5%, five hundred win 62.5%. Beyond that the effect flattens: 2,500 reviews (67.5%) is not significantly different from 500 (p = 0.39). The biggest gain sits between 25 and 100 reviews.


### A new brand does not need fame. It needs a rating the model can trust

Across this series, public fame explains almost nothing about what the model recommends, and the model's own past behaviour explains a lot. That leaves new brands with a narrow door: verifiable evidence in the model's context. This study sizes the door. In these tests the entry price was a rating of at least 4.4 stars backed by a few dozen reviews, and the effect grows with both. Press coverage and sales volume did not substitute for it.

For a small brand this changes the order of work. Collecting the first 25 to 100 reviews and keeping the rating above 4.4 is worth more, in these tests, than anything that raises awareness without producing a verifiable score. And the review score has to be visible where the model reads it, not only on a page it never fetches.


## Limitations

- A review score is the lever. The review count is what makes the lever work. Neither can be skipped. A count of reviews without a rating does not register, and a rating without a count is only half believed.
- Giving the model only the count ("500 verified reviews", no score) wins 2.5%, no different from no evidence (p = 0.061). Giving it only the score ("4.7 stars", no count) wins 26.4%. Both together win 62.5%. The combination beats either part alone (p = 0.0004 for both comparisons).
- Across this series, public fame explains almost nothing about what the model recommends, and the model's own past behaviour explains a lot. That leaves new brands with a narrow door: verifiable evidence in the model's context. This study sizes the door. In these tests the entry price was a rating of at least 4.4 stars backed by a few dozen reviews, and the effect grows with both. Press coverage and sales volume did not substitute for it.
- For a small brand this changes the order of work. Collecting the first 25 to 100 reviews and keeping the rating above 4.4 is worth more, in these tests, than anything that raises awareness without producing a verifiable score. And the review score has to be visible where the model reads it, not only on a page it never fetches.
- The newcomer is an invented brand and the review facts are written into the prompt. This tests how the model weighs a described review record, not how it reads real review pages.
- The incumbent got no score, to isolate the newcomer's evidence. A real incumbent has its own rating and reviews, so real-world selection rates for a newcomer will be lower than these.
- 4.7 stars on 5 reviews is rare in reality. Separating the two shows which does what, but some combinations (high rating, tiny count) are cleaner in the lab than in a real marketplace.
- Everything is gpt-4o on one set of intents. At 100 reviews the newcomer's rate ranges from 30% (electronics) to 70% (home) by category; the sample is too small to say whether that spread is real.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Under 4.1 Stars, the Model Ignores an Unknown Brand. At 4.9 Stars It Picks It 85% of the Time.* Recommendation Intelligence Research™, Study #46. https://atomfoundry.dev/research/cold-start-dose-response. https://doi.org/10.5281/zenodo.23350992
