# Press Coverage Moves the Model Only When It Answers the Exact Question Asked. Generic: 1.9%. Matching: 80.6%.

Atom Foundry — Recommendation Intelligence Research™ · Study #48
Published: 2026-10-08
DOI: [10.5281/zenodo.23351108](https://doi.org/10.5281/zenodo.23351108)

## Headline result

Cold Start found that press coverage barely moves an unknown brand (1.9%) while a review score does (53.1%). We asked what a third-party mention would have to contain to matter. A mention that carries verifiable facts works like the same facts shown directly. A mention that names the brand for the exact query the shopper asked works far better still. The same endorsement for a neighbouring use case, or for a different product category, does nothing.

## Key figures

- **1.9%** — Generic press
- **15.0%** — Category-level
- **80.6%** — Exact query
- **96.9%** — Query + facts

## Design summary

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents from Cold Start
- **Main run:** 6 conditions, 2,160 calls
- **Control run:** 3 conditions, 1,080 calls, added after the main result
- **Facts clause:** 4.7 stars across 500 verified customer reviews, identical wherever used
- **Scoring:** exact brand match on the model's answer, no judge
- **Calls:** 3,240 (36 intents × 9 conditions × 10 runs)
- **Statistics:** cluster bootstrap over intents, permutation tests, Bonferroni

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-newcomer-selection-rate.svg` / `.png` — Newcomer selection rate
- `Charts/02-newcomer-selection-rate-by-what-the-press-line-names.svg` / `.png` — Newcomer selection rate by what the press line names

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/press-with-facts

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Press Coverage Moves the Model Only When It Answers the Exact Question Asked. Generic: 1.9%. Matching: 80.6%.* Recommendation Intelligence Research™, Study #48. https://atomfoundry.dev/research/press-with-facts. https://doi.org/10.5281/zenodo.23351108
