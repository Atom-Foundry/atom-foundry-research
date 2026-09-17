# Nothing About Your Brand Predicts Recommendation. The Model's Own Past Behavior Does.

**Atom Foundry -- Recommendation Intelligence Research(TM), Study #7**
**Published:** July 2026 (Part seven of the series)
**Live page:** https://atomfoundry.dev/research/the-model-predicts-itself

## Summary

Store quality explains 0.7% of who gets recommended. Public fame explains
1.2%. Web traces explain 0.2%. Intent, the one factor that separates
recommended stores from the rest, explains 1.2% of frequency once a brand
is already in. Four independent external signals, four numbers within a
rounding error of zero.

Then the study asked a different question: does what the model recommended
last month predict what it recommends this month? That number is 61.4%,
and it still has not moved after 15 days.

## Headline numbers

| Metric | Value |
|---|---|
| Brand-intent pairs, month to month | 1,082 |
| R-squared, position predicts position (Pearson) | 61.4% |
| Weakest external signal (web traces) | 0.2% |
| Drift after 15 days | 0 pts |

## Files

- `README.md` -- this file
- `methodology.md` -- full design, statistics, and limitations, reproduced from the published page
- `data.csv` -- R-squared for each of the four external signals plus the internal (month-to-month position) signal
- `Charts/external_vs_internal_signal.png` -- bar chart of the core finding

## Data source and scope

All numbers in this package are the aggregate, already-published results
shown on the live study page. No row-level / per-call raw data is included
in this package.

## How to cite

DOI pending (Zenodo record not yet minted for this study). Cite as:

Atom Foundry (2026). *Nothing About Your Brand Predicts Recommendation.
The Model's Own Past Behavior Does.* Recommendation Intelligence
Research(TM), Study #7. https://atomfoundry.dev/research/the-model-predicts-itself

## Related studies

- Two Months Later, the Model Still Agrees With Itself: https://atomfoundry.dev/research/recommendation-lock-in
- The State of AI Recommendations Across Commerce 2026: https://atomfoundry.dev/research/ai-recommendations-across-commerce-2026
