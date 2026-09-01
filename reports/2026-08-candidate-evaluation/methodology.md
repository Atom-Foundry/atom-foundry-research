# Methodology

## Study

**Hand It a Rating, and It Follows Every Single Time**  
Study #19 · Published 2026-08-27

Source page: https://atomfoundry.dev/research/candidate-evaluation

## Design

Phase 1 used 50 open prompts with ten runs each to identify contests where the top two brands were within four wins of one another. Two apparent contests were removed because the two names were actually the same brand or sub-brand. Phase 2 established a paired no-data baseline for the remaining 16 pairs. Phase 3 repeated each pair with one injected fact block at a time: price/availability, rating/review count, or specification depth. Results were evaluated as both raw follow-the-better-number rates and flip rates relative to the paired baseline, with cluster bootstrap intervals and permutation tests.

## Experimental parameters

- Model: gpt-4o
- Temperature: 0.7
- 50 open shopping intents across 10 categories
- 16 genuinely contested brand pairs after Phase 1
- Phase 2: 16 pairs × 10 no-data baseline runs = 160
- Phase 3: 16 pairs × 3 signals × 10 runs = 480
- 1,140 total model calls

## Primary outcomes

- A better rating + review count was followed in 160/160 runs (100%).
- A deeper spec list was followed in 81.9% of runs.
- Better price + availability was followed in 60.6% of runs.
- Against the paired no-data baseline, rating flipped 50.0% of runs (p<0.0001), specs 41.9% (p=0.0004), price 26.9% (p=0.055).
- Rating beat price by 23.1 percentage points in a Bonferroni-adjusted pairwise test (p=0.0012).
- The paired no-data noise floor was 11.2%.

## Data handling and limitations

The methodology and limitations below are reproduced from the published HTML where stated. No additional experimental assumptions are introduced here. Values in the accompanying CSV are transcribed from the visible research page and its embedded chart labels.

## Reproducibility note

This repository package was reconstructed from the published Atom Foundry HTML page. It contains the study-level summary, the values explicitly exposed by the page, and charts regenerated from those published values. It does not claim to recreate any underlying raw model-response dataset that is not exposed in the HTML.
