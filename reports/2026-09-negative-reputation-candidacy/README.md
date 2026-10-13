# A Bad Rating Barely Touches Candidacy. It Wrecks the Final Round.

Atom Foundry — Recommendation Intelligence Research™ · Study #42
Published: 2026-09-28
DOI: [10.5281/zenodo.23350436](https://doi.org/10.5281/zenodo.23350436)

## Headline result

A LinkedIn commenter argued that AI pre-filters bad actors before they ever get mentioned, so a mention itself is a reasonable proxy for success. We tested that directly on 4 brands reused from Winner vs Loser: a neutral system context against a disclosed-synthetic negative reputation, low rating, review count, one generic non-safety complaint. Two probes, an open buyer question and a forced two-way comparison against a named competitor. The result is the opposite of the pre-filtering theory. Candidacy rate went up under negative reputation, 39.0% to 54.5%. The forced-selection win rate collapsed, 83.5% to 24.3%.

## Key figures

- **+15.5pp** — Candidacy rose, not fell
- **-59.2pp** — Selection win rate collapsed
- **4** — Brands tested
- **2,400** — Chat + judge calls

## Design summary

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Winner vs Loser
- **Conditions:** neutral vs. negative reputation
- **Probe A, candidacy:** open buyer question, brand_mentioned string match
- **Probe B, selection:** forced two-way vs. named competitor, LLM judge
- **Total calls:** 1,600 chat (800 per probe), 800 judge on Probe B

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-candidacy-vs-selection-rate-neutral-vs-negative-reputation.svg` / `.png` — Candidacy vs. selection rate, neutral vs. negative reputation

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/negative-reputation-candidacy

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *A Bad Rating Barely Touches Candidacy. It Wrecks the Final Round.* Recommendation Intelligence Research™, Study #42. https://atomfoundry.dev/research/negative-reputation-candidacy. https://doi.org/10.5281/zenodo.23350436
