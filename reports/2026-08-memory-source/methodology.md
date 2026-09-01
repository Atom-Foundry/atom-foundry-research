# Methodology

## Study

**We Widened the Fame Signal Four Ways. It Barely Moved**  
Study #21 · Published 2026-08-27

Source page: https://atomfoundry.dev/research/memory-source

## Design

The study reused the closed-book recommendation baseline from Cold Start. For each distinct brand, four free public signals were collected: 12-month Wikipedia pageviews, Wikidata sitelinks, domain age in days, and 12-month GDELT media mention volume capped at 250 records. Individual correlations/regressions were tested against recommendation frequency, then all four signals were combined for a multiple regression on the 50 brands with complete data. Cluster bootstrap confidence intervals and significance tests were used. A stricter 75-brand inclusion threshold was also evaluated.

## Experimental parameters

- Model: gpt-4o
- Temperature: 0.7
- Closed-book baseline reused from Cold Start, no new model calls
- 95 distinct brands
- 4 public footprint signals per brand
- ~380 free public API/WHOIS lookups
- 50 brands with all four signals present
- Multiple regression with bootstrap analysis

## Primary outcomes

- Wikipedia pageviews alone: R² 2.3%, p=0.135.
- Wikidata sitelinks: R² 0.9%, p=0.365.
- Domain age: R² 2.2%, p=0.147.
- GDELT media mentions: R² 5.2%, p=0.095.
- All four combined: R² 11.2%.
- A stricter 75-brand cut produced a combined R² of 6.1%.
- All footprint signals remain far below the 61.4% self-consistency benchmark.

## Data handling and limitations

The methodology and limitations below are reproduced from the published HTML where stated. No additional experimental assumptions are introduced here. Values in the accompanying CSV are transcribed from the visible research page and its embedded chart labels.

## Reproducibility note

This repository package was reconstructed from the published Atom Foundry HTML page. It contains the study-level summary, the values explicitly exposed by the page, and charts regenerated from those published values. It does not claim to recreate any underlying raw model-response dataset that is not exposed in the HTML.
