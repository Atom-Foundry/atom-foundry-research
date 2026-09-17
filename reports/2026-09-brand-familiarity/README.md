# Claim the Brand Is Widely Known, and It Wins 80% of the Time

**Bring in a rating, and the edge is nearly gone.**

Atom Foundry — Recommendation Intelligence Research™ · Study #35
Published: 2026-09-15
DOI: [10.5281/zenodo.22778177](https://doi.org/10.5281/zenodo.22778177)

## Headline result

When a plain, unsourced familiarity claim ("widely recognized brand") is the only differentiating signal, the brand carrying it wins **79.8%** of forced-choice comparisons (n=1,600, both independent rounds combined, p<1e-60 both rounds).

Once a rating signal is added, familiarity's own marginal contribution nearly vanishes: **+0.2 points** (55.6% vs 55.4% combined) — an order of magnitude smaller than rating's own ~88-point swing, and round 2 alone showed an exact 0.0pp gap.

## Design summary

- 4 ecommerce brands: same set as the Authority Signal study — Barbaro Mojo (functional), Hearthloom (functional), Colored Organics (trust), BodyArtForms (trust)
- 2 phases: Phase 1 isolates familiarity alone (2 conditions); Phase 2 crosses familiarity with rating in a full 2x2 (4 conditions)
- 20 purchase intents x 5 repeats per cell, 2 independent rounds with fresh random seeds
- 4,800 total GPT-4o calls (2,400 per round)
- Forced two-way pick, brand order randomized per call, GPT-4o LLM judge for winner determination
- 0 judge parse failures out of 4,800 calls

## Package contents

- `README.md` — this file
- `methodology.md` — full method, statistics, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/familiarity_follow_rate_by_brand.png` — Phase 1 follow-rate by brand
- `Charts/rating_dominates_familiarity_marginal_lift.png` — Phase 1 vs Phase 2 comparison

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.co/research/brand-familiarity.html

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Claim the Brand Is Widely Known, and It Wins 80% of the Time.* Recommendation Intelligence Research™, Study #35. Zenodo. https://doi.org/10.5281/zenodo.22778177
