# Rating Recommendations Don't Move When You Reword the Question. Price Recommendations Do.

Atom Foundry — Recommendation Intelligence Research™ · Study #41
Published: 2026-09-22
DOI: [10.5281/zenodo.23350256](https://doi.org/10.5281/zenodo.23350256)

## Headline result

Recommendation Confidence's Method 6 asked the same 16 contested intents five differently worded ways and found the pick never moved, 0 of 16 flipped, only the hedge language shifted. That page's own limitations section flagged the gap directly: the design was only ever run on the rating signal, price and specs were untested. This study closes it, same 16 intents, same 5 phrasings, same 10-runs-per-phrasing design, run on the price and specs fact pairs instead. The rating signal's stability does not generalize. Price picks flipped in 7 of 16 intents, a 43.8-point gap versus rating that clears significance after correction (p=0.0225). Specs picks flipped in 2 of 16, numerically double rating's rate but not statistically significant at this sample size.

## Key figures

- **+43.8pp** — Price vs. rating flip-rate gap (p=0.0225, significant)
- **0** — Rating intents flipped, of 16 (published)
- **2** — Specs intents flipped, of 16 (not significant)
- **7** — Price intents flipped, of 16 (significant)

## Design summary

- **Model:** gpt-4o, temperature 0.7
- **Design:** 16 contested intents × 5 phrasings × 10 runs, per signal
- **Total calls:** 1,600 (800 price, 800 specs)
- **Pick extraction:** majority vote of 10 runs per phrasing, identical rule to published Method 6
- **Statistics:** cluster-permutation test, unit=intent (n=16 per signal), 10,000 permutations
- **Correction:** Bonferroni ×3 (price vs. rating, specs vs. rating, price vs. specs)

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-share-of-intents-where-the-pick-flipped-across-5-phrasings-b.svg` / `.png` — Share of intents where the pick flipped across 5 phrasings, by signal type

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/phrasing-stability-by-signal

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Rating Recommendations Don't Move When You Reword the Question. Price Recommendations Do.* Recommendation Intelligence Research™, Study #41. https://atomfoundry.dev/research/phrasing-stability-by-signal. https://doi.org/10.5281/zenodo.23350256
