# Methodology

## Study

**We Invented a Brand With Zero History. Reviews Got It Picked Anyway**  
Study #20 · Published 2026-08-27

Source page: https://atomfoundry.dev/research/cold-start

## Design

Phase 1 identified entrenched leaders from 50 open intents, requiring the top brand to win at least 7 of 10 runs. Phase 2 paired each leader with an invented brand that had no training-data footprint and supplied no evidence. Phase 3 repeated the same pair while injecting one evidence type at a time: review score, press mention, or sales-volume claim. The invented names were created for the study and were not checked against a trademark database. A stricter ≥8/10 robustness cut was also tested.

## Experimental parameters

- Model: gpt-4o
- Temperature: 0.7
- 50 open prompts, 10 runs each
- 36 entrenched category leaders selected by top brand winning ≥7/10
- 360 paired runs with zero evidence
- 1,080 evidence-injection runs
- 1,940 total model calls
- 10 invented brand names across categories

## Primary outcomes

- The invented brand won 0/360 runs with zero evidence.
- With an injected review score it won 53.1% of runs (p<0.0001).
- Press mentions produced 1.9% wins (p=0.241).
- Sales-volume claims produced 0.3% wins (p=1.000).
- At a stricter ≥8/10 incumbent threshold, reviews still won 47.8%, press 0.7%, volume 0.0%.

## Data handling and limitations

The methodology and limitations below are reproduced from the published HTML where stated. No additional experimental assumptions are introduced here. Values in the accompanying CSV are transcribed from the visible research page and its embedded chart labels.

## Reproducibility note

This repository package was reconstructed from the published Atom Foundry HTML page. It contains the study-level summary, the values explicitly exposed by the page, and charts regenerated from those published values. It does not claim to recreate any underlying raw model-response dataset that is not exposed in the HTML.
