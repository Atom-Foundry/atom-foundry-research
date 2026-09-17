# Give It the Better Rating, and It Wins 91% of the Time

**Two signals we thought would matter next, barely do.**

Atom Foundry — Recommendation Intelligence Research™ · Study #33
Published: 2026-09-15
DOI: [10.5281/zenodo.22777385](https://doi.org/10.5281/zenodo.22777385)

## Headline result

With rating, claim specificity, and message format all competing in the same decision (full 2x2x2 factorial, n=6,400), the target brand's winner matches whichever brand carries the stronger rating **90.8%** of the time.

- **Rating**: target wins 99.2% when it has the stronger rating, 17.6% when the competitor does — the dominant signal
- **Specificity**: replicated in both independent rounds, 55.5% (vague) vs 61.3% (specific), a **+5.8 point** gain (p<0.001 both rounds)
- **Format**: not confirmed. Prose 59.5% vs structured bullets 57.3% — did not reach significance in either round alone (p=0.25, p=0.15)

## Design summary

- 4 ecommerce brands: same set used in the PDP Specificity study's first round — Barbaro Mojo, Hearthloom (functional), Colored Organics, BodyArtForms (trust)
- Full 2x2x2 factorial: rating (target/competitor stronger) x specificity (vague/specific) x format (prose/structured) = 8 conditions per brand
- 20 purchase intents x 5 repeats per cell, 2 independent rounds with fresh random seeds
- 6,400 total GPT-4o calls (3,200 per round)
- GPT-4o LLM judge for winner determination, 0 parse failures out of 6,400 calls

## Package contents

- `README.md` — this file
- `methodology.md` — full method, statistics, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/three_signals_compared.png` — rating vs specificity vs format, head to head
- `Charts/by_brand_no_reversal.png` — category x specificity by brand, showing no reversal once a real competitor rating is present

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.co/research/winner-vs-loser.html

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Give It the Better Rating, and It Wins 91% of the Time.* Recommendation Intelligence Research™, Study #33. Zenodo. https://doi.org/10.5281/zenodo.22777385
