# Mark the Listing Sponsored, and It Loses 18.4 Points in a Head-to-Head Pick

Atom Foundry — Recommendation Intelligence Research™ · Study #43
Published: 2026-09-28
DOI: [10.5281/zenodo.23350804](https://doi.org/10.5281/zenodo.23350804)

## Headline result

Two outside numbers disagreed about paid placement. Zhao Hanbo (Nile) measured a near-zero effect across 3,602 ChatGPT ad placements, -0.3pp. A separate academic paper (Allouah et al., ACM Web Conference 2026) found agents actively penalize a sponsored tag, and Juozas Kaziukenas showed Meta Muse never once shortlisted a sponsored Walmart listing. We tested it directly: 4 brands, one factor, a target brand's listing described as a standard result or a Sponsored result, competitor always standard, forced two-way comparison. Organic won 74.2% of the time. Sponsored won 55.8%.

## Key figures

- **-18.4pp** — Sponsored tag penalty
- **74.2%** — Organic win rate
- **55.8%** — Sponsored win rate
- **4** — Brands, all 4 same direction

## Design summary

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Winner vs Loser
- **Conditions:** organic vs. sponsored label, target only
- **Comparison:** forced two-way vs. named competitor, LLM judge
- **Total calls:** 800 chat, 800 judge (all rows judged)
- **Judge prompt:** unchanged from Winner vs Loser

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-selection-winner-rate-by-condition.svg` / `.png` — Selection/winner rate by condition

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/sponsored-tag-penalty

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Mark the Listing Sponsored, and It Loses 18.4 Points in a Head-to-Head Pick* Recommendation Intelligence Research™, Study #43. https://atomfoundry.dev/research/sponsored-tag-penalty. https://doi.org/10.5281/zenodo.23350804
