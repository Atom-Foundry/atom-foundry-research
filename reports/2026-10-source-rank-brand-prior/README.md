# In a Ranked Source, the Higher-Ranked Brand Wins 100% of the Time, Even Against the Model's Favorite.

Atom Foundry — Recommendation Intelligence Research™ · Study #47
Published: 2026-10-07
DOI: [10.5281/zenodo.23351061](https://doi.org/10.5281/zenodo.23351061)

## Headline result

Study #45 showed that a brand at rank 1 of a cited source is picked every time and a brand at rank 4 almost never. That left open whether the model believes the ranking or simply follows the prompt. We ran the full set of challenges: removing the instruction, moving the source, using real brands, varying the source's reliability, pitting rank against reviews, and listing the same brands without a ranking. Rank holds in every one of them. It is an order, not a slope: the higher brand won in every pair we tried, from adjacent places to a fourteen-place gap.

## Key figures

- **100.0%** — Ranked #1 vs favorite
- **0.0%** — Ranked #2 vs favorite
- **0.8%** — Unordered list
- **86.1%** — #1 with 3.4 stars

## Design summary

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents (16 with a real challenger)
- **Position:** newcomer at #1, #2, #3, #4, #5, #8, #15 against a favorite at #1, #2, #3, #8, #15
- **Prompt:** instruction on, off, or neutral; source in system or user message
- **Source:** authoritative, anonymous blog, sponsored list
- **Evidence:** none, 3.4 stars, 4.7 stars, 4.9 stars (2,500 reviews)
- **Controls:** no source; same brands in an unordered list
- **Calls:** 12,720 across three runs (2,880 + 8,400 + 1,440)

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-newcomer-selection-rate.svg` / `.png` — Newcomer selection rate
- `Charts/02-newcomer-selection-rate-by-rank-pair.svg` / `.png` — Newcomer selection rate by rank pair
- `Charts/03-newcomer-ranked-1-favorite-2.svg` / `.png` — Newcomer ranked #1, favorite #2
- `Charts/04-newcomer-ranked-4-favorite-2.svg` / `.png` — Newcomer ranked #4, favorite #2

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/source-rank-brand-prior

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *In a Ranked Source, the Higher-Ranked Brand Wins 100% of the Time, Even Against the Model's Favorite.* Recommendation Intelligence Research™, Study #47. https://atomfoundry.dev/research/source-rank-brand-prior. https://doi.org/10.5281/zenodo.23351061
