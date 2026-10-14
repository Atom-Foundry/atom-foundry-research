# Methodology

## Study

**Two Months Later, the Model Still Agrees With Itself**  
Study #18 · Published 2026-08-26

Source page: https://atomfoundry.dev/research/recommendation-lock-in

## Design

The same 50 intents were submitted repeatedly to gpt-4o-mini at temperature 0.7. Each sweep contained ten runs per intent. Six sweeps were collected over 58 days. The primary outcome was binary: whether the exact same brand occupied position #1 in every sweep. Three borderline cases were re-run at 20 samples to separate persistent disagreement from small-sample noise. Two sweep identifiers were corrected after tracing execution timestamps and splitting a duplicated same-day identifier.

## Experimental parameters

- Model: gpt-4o-mini
- Temperature: 0.7
- 50 shopping intents across 10 categories
- 6 independent sweeps, June 30–August 26 2026
- 10 runs per intent per sweep
- 30,170 recommendations analyzed
- Concordance rule: exact same #1 brand in every sweep
- 7 non-concordant intents received a 20-run same-day confirmatory check

## Primary outcomes

- 43 of 50 intents (86%) returned the exact same #1 brand in every sweep.
- 7 of 50 intents (14%) changed #1 at least once.
- Two of the three borderline cases tested at 20 runs resolved as sampling noise.
- Ceramic dinnerware remained a genuine split: Fiesta 50%, Corelle 40% at 20 runs.
- Category specialists averaged position 1.6 versus 7.4 for broad generalist retailers in the supporting comparison.

## Data handling and limitations

The methodology and limitations below are reproduced from the published HTML where stated. No additional experimental assumptions are introduced here. Values in the accompanying CSV are transcribed from the visible research page and its embedded chart labels.

## Reproducibility note

This repository package was reconstructed from the published Atom Foundry HTML page. It contains the study-level summary, the values explicitly exposed by the page, and charts regenerated from those published values. It does not claim to recreate any underlying raw model-response dataset that is not exposed in the HTML.
