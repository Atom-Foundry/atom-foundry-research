# Rank First in the Cited Source, and the Model Always Agrees. Fourth Place Wins 1.2% of the Time.

Atom Foundry — Recommendation Intelligence Research™ · Study #45
Published: 2026-09-28
DOI: [10.5281/zenodo.23350942](https://doi.org/10.5281/zenodo.23350942)

## Headline result

Inspired by a LinkedIn exchange with Olga Vainshtok: a company in her AEO audit sat 4th of 17 in a "brand alternatives" roundup, and none of the five engines she tested named it. We isolated the variable. Same 4 brands, same synthetic 17-slot source, only the target's rank moved. Selection rate: 100% at rank 1, 1.2% at rank 4, 0% at rank 15. Candidacy barely moves at all: 100%, 40%, 35.2%.

## Key figures

- **100.0%** — Selection rate at rank 1
- **1.2%** — Selection rate at rank 4
- **0.0%** — Selection rate at rank 15
- **100.0pp** — Rank 1 minus rank 15

## Design summary

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Winner vs Loser
- **Conditions:** rank_1, rank_4, rank_15 (target's slot in the cited source)
- **Comparison:** forced two-way vs. named competitor, LLM judge
- **Calls:** 1,200 chat, 1,200 judge
- **Judge parse failures:** 0 of 1,200

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-selection-winner-rate-by-source-rank.svg` / `.png` — Selection/winner rate by source rank
- `Charts/02-named-candidacy-rate-by-source-rank.svg` / `.png` — Named-candidacy rate by source rank

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/source-rank-position

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Rank First in the Cited Source, and the Model Always Agrees. Fourth Place Wins 1.2% of the Time.* Recommendation Intelligence Research™, Study #45. https://atomfoundry.dev/research/source-rank-position. https://doi.org/10.5281/zenodo.23350942
