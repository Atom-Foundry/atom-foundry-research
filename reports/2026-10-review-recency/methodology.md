# Methodology — Reviews Four Years Old Count as No Reviews at All: 0%. Five Hundred Fresh Ones Beat Thirty Thousand Old Ones, 72.8% to 1.4%. (Study #50)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents from Cold Start
- **Conditions:** 12, each a single fixed review line
- **Age wording:** “all posted in the last 3 months”, “all posted 4 years ago”, “posted evenly over the past 5 years”
- **Scoring:** exact brand match on the model's answer, no judge
- **Calls:** 4,320 (36 intents × 12 conditions × 10 runs)
- **Contrasts:** 9 pre-planned, Bonferroni-corrected
- **Statistics:** cluster bootstrap over intents, permutation tests

## Pre-registration and data

Pre-registration. All predictions and the nine contrasts were written before the run. Every number on this page is in the study's results file.

## Results table

| Newcomer's review line | Newcomer selected | 95% CI (bootstrap over intents) |
|---|---|---|
| 4.7 stars, 500 reviews, all from the last 3 months | 72.8% | 61.7–83.3% |
| 4.7 stars, 30,000 reviews, no dates | 71.1% | 59.4–81.9% |
| 4.7 stars, 500 reviews, posted evenly over 5 years | 60.8% | 48.9–72.5% |
| 4.7 stars, 500 reviews, no dates | 50.8% | 38.9–62.5% |
| 4.7 stars, 40 reviews, all from the last 3 months | 36.9% | 25.8–48.9% |
| 4.7 stars, 40 reviews, no dates | 22.5% | 13.1–33.1% |
| 3.8 overall, 4.7 over the last 3 months (500 reviews) | 10.6% | 4.4–18.1% |
| 4.7 overall, 3.8 over the last 3 months (500 reviews) | 2.5% | 0.3–5.3% |
| 4.7 stars, 30,000 reviews, all posted 4 years ago | 1.4% | 0.0–3.6% |
| 4.7 stars, 500 reviews, all posted 4 years ago | 0.0% | 0.0–0.0% |
| 4.7 stars, 500 reviews: 450 posted 4 years ago, 50 in the last 3 months | 0.0% | 0.0–0.0% |
| 3.8 stars, 500 reviews, no dates | 0.0% | 0.0–0.0% |

## Findings and interpretation (from the study page)

### We measured the rating and the count. Never the age.

Cold Start found that review evidence is what moves an unknown brand against an entrenched incumbent. Cold Start Dose-Response showed how: the rating mostly, the count second. In both, reviews were undated. A practitioner in a LinkedIn exchange raised the obvious next question: if models and agents prefer recent feedback, then 30,000 reviews from the early 2020s would matter far less than they appear to. We did not know, and said so.

We wrote five predictions down before running. Old reviews lower selection compared with undated ones; fresh reviews do not; age discounts even a very large count, and a few hundred fresh reviews are worth at least as much as thousands of old ones; the rating over the last three months overrides the overall rating in both directions; and simply stating dates changes nothing. All five held, and the first and fourth by wide margins.


### One review line, twelve versions

Same setup as Cold Start Dose-Response: 36 intents where one brand already dominates the model's open answers, each paired with an invented newcomer. The incumbent gets a neutral line (“an established, widely available brand”). The newcomer gets one review line: 4.7 stars in most conditions, 500 reviews or 30,000 or 40, and the only thing that changes is when they were posted. Brand order is randomized per run.


### Four-year-old reviews do the work of no reviews at all

With a rating of 4.7 stars and 500 reviews fixed, reviews all posted in the last three months were chosen 72.8% of the time, against 50.8% when no dates were given (+21.9 points, p = 0.0009 after correction). Reviews all posted four years ago were chosen 0.0% of the time, the same as an unknown brand with no evidence in Cold Start. Mixing in 50 recent reviews among 450 old ones did not help: 0.0%. Merely stating that reviews were spread over five years did not hurt: 60.8%, not significantly different from undated.


### Age beats volume. 500 fresh reviews beat 30,000 old ones

Thirty thousand reviews with no dates were chosen 71.1% of the time. The same thirty thousand posted four years ago: 1.4%, a drop of 69.7 points. Five hundred recent reviews beat thirty thousand old ones by 71.4 points (72.8% to 1.4%, p = 0.0009). At the small end, forty reviews posted in the last three months were chosen 36.9% of the time against 22.5% for forty undated ones (+14.4 points, p = 0.0099). Age works as a multiplier on the count: a large count does not protect old reviews.


### The last three months override the overall rating

With an overall rating of 4.7 stars but 3.8 stars over the last three months, the newcomer was chosen 2.5% of the time, against 50.8% for a plain 4.7 (−48.3 points, p = 0.0009). The reverse helps only partly: an overall 3.8 with 4.7 over the last three months reached 10.6%, against 0.0% for a plain 3.8 (+10.6 points, p = 0.0045), but stayed far below the 50.8% of a plain 4.7. A recent decline is punished almost fully. A recent recovery is rewarded only a little.


### Reviews are a flow, not a stock

In this setting, a large archive of reviews does not protect a brand once the reviews are old. What counted was how recent the evidence was: a few hundred fresh reviews did the work of thousands without dates, and old ones did the work of none. A recent drop in rating outweighed a strong overall score almost completely. For a store, that points to review velocity and to what customers say now, rather than to the total count on the page.

This extends what earlier studies measured about review evidence. Cold Start showed that reviews are what lets an unknown brand through. Dose-Response showed how much rating and count each contribute. This adds the third dimension, and it is not a small one: age decided whether the evidence counted at all.


## Limitations

- The review line is placed in the prompt with a stated age. This measures how the model weighs a described age, not how real shopping agents filter or sort reviews by date.
- “All posted 4 years ago” may be read as older feedback, or as a brand with no recent activity. We cannot separate the two. The 450 old plus 50 recent condition, which also scored 0.0%, suggests the model weighs the old majority heavily either way.
- Ages are relative (“4 years ago”, “last 3 months”) because the model has no reliable sense of today's date. Other phrasings or absolute dates may behave differently.
- Invented newcomers, gpt-4o, forced two-way choice against an incumbent. Other models, real brands and open-ended answers may weigh review age differently.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Reviews Four Years Old Count as No Reviews at All: 0%. Five Hundred Fresh Ones Beat Thirty Thousand Old Ones, 72.8% to 1.4%.* Recommendation Intelligence Research™, Study #50. https://atomfoundry.dev/research/review-recency. https://doi.org/10.5281/zenodo.23351282
