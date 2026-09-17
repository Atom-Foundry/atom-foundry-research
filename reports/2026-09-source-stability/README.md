# The Cited Source Changes. The Winner Almost Never Does.

**Atom Foundry -- Recommendation Intelligence Research(TM), Study #36**
**Published:** September 2026
**Live page:** https://atomfoundry.dev/research/source-stability

## Summary

Live Retrieval found that when ChatGPT's web search actually fires, it
returns real citations, but which pages it cites is not fixed -- ask the
identical question twice and search can surface a different page each
time. This study asks the next question directly: when the cited source
changes between repeats of the same prompt, does the recommended brand
change with it.

Eight real product categories, ten independent repeats each, two full
rounds, real competing brands instead of this series' usual synthetic
four (live search needs real content to find). Across the categories
where the comparison could actually be run, the winner stayed the same
brand about 90% of the time regardless of which exact domains search
happened to cite that round, and a cluster-level test found no measurable
link between which domain got cited and which brand won.

## Headline numbers

| Metric | Value |
|---|---|
| Winner stability, 8 categories | 90% |
| Search invocation rate | 100% |
| Cluster-level difference (winner stability vs. source overlap) | +7.9pp, not significant |
| Real categories, both rounds | 8 |

## Files

- `README.md` -- this file
- `methodology.md` -- full design, statistics, worked example, robustness checks, and limitations, reproduced from the published page
- `data.csv` -- winner stability and source stability by category, both rounds
- `Charts/winner_stability_by_category.png` -- bar chart of the core finding

## Data source and scope

All numbers in this package are the aggregate, already-published results
shown on the live study page. No row-level / per-call raw data is included
in this package.

## How to cite

DOI pending (Zenodo record not yet minted for this study). Cite as:

Atom Foundry (2026). *The Cited Source Changes. The Winner Almost Never
Does.* Recommendation Intelligence Research(TM), Study #36.
https://atomfoundry.dev/research/source-stability

## Related studies

- Study #28, Live Retrieval: https://atomfoundry.dev/research/live-retrieval
- Two Months Later, the Model Still Agrees With Itself: https://atomfoundry.dev/research/recommendation-lock-in
