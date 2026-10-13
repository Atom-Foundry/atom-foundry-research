# Match the Sponsored Listing to the Search Term, and the Penalty Overshoots by 21 Points

Atom Foundry — Recommendation Intelligence Research™ · Study #44
Published: 2026-09-28
DOI: [10.5281/zenodo.23350889](https://doi.org/10.5281/zenodo.23350889)

## Headline result

Direct follow-up to the Sponsored Tag Penalty (Study #43, -18.4pp). One outside paper claims sellers can partially defend against the penalty with query-conditional descriptions, text that adapts to the exact search term instead of staying static. We tested it on the same 4 brands, changing one sentence. It didn't just recover the penalty. It blew past the organic baseline entirely: static sponsored 55.8%, organic reference 74.2%, query-matched sponsored 95.2%.

## Key figures

- **+39.4pp** — Recovery vs. static sponsored
- **95.2%** — Query-conditional win rate
- **214.1%** — Of the organic-static gap closed
- **4** — Brands, all 4 same direction

## Design summary

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Study #43
- **Conditions:** static sponsored (reused) vs. query-conditional sponsored (new)
- **Comparison:** forced two-way vs. named competitor, LLM judge
- **New calls:** 400 chat, 400 judge (static reused, 0 new)
- **Judge prompt:** unchanged from Study #43 / Winner vs Loser

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-selection-winner-rate-by-condition.svg` / `.png` — Selection/winner rate by condition

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/query-conditional-defense

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Match the Sponsored Listing to the Search Term, and the Penalty Overshoots by 21 Points* Recommendation Intelligence Research™, Study #44. https://atomfoundry.dev/research/query-conditional-defense. https://doi.org/10.5281/zenodo.23350889
