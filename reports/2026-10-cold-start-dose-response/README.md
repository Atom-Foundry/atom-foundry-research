# Under 4.1 Stars, the Model Ignores an Unknown Brand. At 4.9 Stars It Picks It 85% of the Time.

Atom Foundry — Recommendation Intelligence Research™ · Study #46
Published: 2026-10-06
DOI: [10.5281/zenodo.23350992](https://doi.org/10.5281/zenodo.23350992)

## Headline result

Cold Start showed that an unknown brand wins 0 of 360 comparisons with no evidence and 53.1% with a review score. It did not say how much review evidence is enough. We varied the dose in fixed steps: review count from 5 to 2,500 at 4.7 stars, and rating from 3.8 to 4.9 stars at 500 reviews. The rating is the lever, and it has a threshold. The review count decides whether the model believes the rating.

## Key figures

- **84.7%** — 4.9 stars, 500 reviews
- **2.8%** — 4.7 stars, only 5 reviews
- **26.4%** — Score only, no count
- **2.5%** — 500 reviews, no score

## Design summary

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents from Cold Start
- **Count arm:** 5, 25, 100, 500, 2,500 reviews at 4.7 stars
- **Rating arm:** 3.8, 4.1, 4.4, 4.7, 4.9 stars at 500 reviews
- **Components:** 4.7 stars with no count; 500 reviews with no score
- **Calls:** 3,960 (36 intents × 11 conditions × 10 runs)
- **Scoring:** exact brand match on the model's answer, no judge
- **Unparseable answers:** 0 of 3,960

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-newcomer-selection-rate-by-rating.svg` / `.png` — Newcomer selection rate by rating
- `Charts/02-newcomer-selection-rate-by-review-count.svg` / `.png` — Newcomer selection rate by review count
- `Charts/03-newcomer-selection-rate-by-evidence-components.svg` / `.png` — Newcomer selection rate by evidence components

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/cold-start-dose-response

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Under 4.1 Stars, the Model Ignores an Unknown Brand. At 4.9 Stars It Picks It 85% of the Time.* Recommendation Intelligence Research™, Study #46. https://atomfoundry.dev/research/cold-start-dose-response. https://doi.org/10.5281/zenodo.23350992
