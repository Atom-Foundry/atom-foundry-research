# Two Signals Get You Most of the Way There. A Third Barely Helps, and Format Doesn't Move It at All.

**Atom Foundry -- Recommendation Intelligence Research(TM), Study #37**
**Published:** September 2026
**Live page:** https://atomfoundry.dev/research/signal-hierarchy

## Summary

Authority, familiarity, and specificity had each been measured alone or
crossed against rating specifically in earlier studies in this series. None
had ever been put head to head against each other, or stacked in
combination, with rating removed from the room entirely. This study runs 12
of the 16 possible combinations of authority, familiarity, specificity, and
format, isolating how these four non-rating signals actually rank and
combine.

Specificity comes out strongest, authority and familiarity trail close
behind and are near-indistinguishable from each other, and format's own
marginal effect rounds to zero. The pattern replicates across 2 independent
rounds run on separate random seeds.

## Headline numbers

| Metric | Value |
|---|---|
| Baseline (zero signals on) | 75.5% |
| Full stack (all four signals) | 99.9% |
| Specificity's own marginal lift (strongest of the four) | +3.25pp |
| Total calls, 2 rounds | 9,600 |

## Files

- `README.md` -- this file
- `methodology.md` -- full design, conditions, statistics, robustness checks, and limitations, reproduced from the published page
- `data.csv` -- winner rate by condition, both rounds where published
- `Charts/winner_rate_by_condition.png` -- bar chart of the core finding

## Data source and scope

All numbers in this package are the aggregate, already-published results
shown on the live study page. No row-level / per-call raw data is included
in this package.

## How to cite

DOI pending (Zenodo record not yet minted for this study). Cite as:

Atom Foundry (2026). *Two Signals Get You Most of the Way There. A Third
Barely Helps, and Format Doesn't Move It at All.* Recommendation
Intelligence Research(TM), Study #37. https://atomfoundry.dev/research/signal-hierarchy

## Related studies

- Study #33, Winner vs Loser: https://atomfoundry.dev/research/winner-vs-loser
- Study #34, Authority Signal: https://atomfoundry.dev/research/authority-signal
- Study #35, Brand Familiarity: https://atomfoundry.dev/research/brand-familiarity
- Study #32, PDP Specificity: https://atomfoundry.dev/research/pdp-specificity
