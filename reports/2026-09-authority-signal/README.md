# Mention It Was Featured Somewhere, and It Wins 85% of the Time

**Bring in a rating, and that edge nearly disappears.**

Atom Foundry — Recommendation Intelligence Research™ · Study #34
Published: 2026-09-16
DOI: [10.5281/zenodo.22777792](https://doi.org/10.5281/zenodo.22777792)

## Headline result

When a third-party authority claim ("featured in X") is the only differentiating signal between two brands, the brand carrying it wins **85.2%** of forced-choice comparisons (n=1,600, both independent rounds combined, p<1e-90 both rounds).

But once a rating signal is added to the same decision, authority's own marginal contribution collapses to **+1.5 points** (56.1% vs 54.6%) — a gap the study's own cluster-permutation test cannot distinguish from noise (p=0.55 round 1, p=0.60 round 2).

## Design summary

- 4 ecommerce brands: Barbaro Mojo (hot sauce, functional), Hearthloom (dinnerware, functional), Colored Organics (baby clothes, trust), BodyArtForms (piercing jewelry, trust)
- 2 phases: Phase 1 isolates authority alone (2 conditions); Phase 2 crosses authority with rating in a full 2x2 (4 conditions)
- 20 purchase intents x 5 repeats per cell, 2 independent rounds with fresh random seeds
- 4,800 total GPT-4o calls (2,400 per round)
- Forced two-way pick, brand order randomized per call, GPT-4o LLM judge for winner determination
- 0 judge parse failures out of 4,800 calls

## Package contents

- `README.md` — this file
- `methodology.md` — full method, statistics, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/authority_follow_rate_by_brand.png` — Phase 1 follow-rate by brand
- `Charts/rating_dominates_authority_marginal_lift.png` — Phase 1 vs Phase 2 comparison

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.co/research/authority-signal.html

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Mention It Was Featured Somewhere, and It Wins 85% of the Time.* Recommendation Intelligence Research™, Study #34. Zenodo. https://doi.org/10.5281/zenodo.22777792
