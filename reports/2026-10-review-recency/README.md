# Reviews Four Years Old Count as No Reviews at All: 0%. Five Hundred Fresh Ones Beat Thirty Thousand Old Ones, 72.8% to 1.4%.

Atom Foundry — Recommendation Intelligence Research™ · Study #50
Published: 2026-10-13
DOI: [10.5281/zenodo.23351282](https://doi.org/10.5281/zenodo.23351282)

## Headline result

A claim keeps coming up in e-commerce circles: AI models and shopping agents favour recent reviews, so a pile of old ones is worth much less than it looks. We had measured the rating and the count of reviews, never their age. With the rating and count held fixed, we varied only the age. Reviews posted four years ago did the same work as no evidence at all, even when there were thirty thousand of them. Five hundred reviews from the last three months beat them 72.8% to 1.4%. And when the rating over the last three months fell below the overall rating, the overall rating stopped mattering.

## Key figures

- **72.8%** — 500 fresh reviews
- **50.8%** — 500, undated
- **0.0%** — 500, 4 years old
- **1.4%** — 30,000, 4 years old

## Design summary

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents from Cold Start
- **Conditions:** 12, each a single fixed review line
- **Age wording:** “all posted in the last 3 months”, “all posted 4 years ago”, “posted evenly over the past 5 years”
- **Scoring:** exact brand match on the model's answer, no judge
- **Calls:** 4,320 (36 intents × 12 conditions × 10 runs)
- **Contrasts:** 9 pre-planned, Bonferroni-corrected
- **Statistics:** cluster bootstrap over intents, permutation tests

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-newcomer-selection-rate-4-7-stars-and-500-reviews.svg` / `.png` — Newcomer selection rate, 4.7 stars and 500 reviews
- `Charts/02-newcomer-selection-rate-4-7-stars.svg` / `.png` — Newcomer selection rate, 4.7 stars
- `Charts/03-newcomer-selection-rate-500-reviews.svg` / `.png` — Newcomer selection rate, 500 reviews

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/review-recency

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Reviews Four Years Old Count as No Reviews at All: 0%. Five Hundred Fresh Ones Beat Thirty Thousand Old Ones, 72.8% to 1.4%.* Recommendation Intelligence Research™, Study #50. https://atomfoundry.dev/research/review-recency. https://doi.org/10.5281/zenodo.23351282
