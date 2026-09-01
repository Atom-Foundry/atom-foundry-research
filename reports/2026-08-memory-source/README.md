# We Widened the Fame Signal Four Ways. It Barely Moved

Recommendation Intelligence Research™ · Atom Foundry · August 2026

---

# Research Summary

The Fame Study found Wikipedia pageviews explained only 1.2% of recommendation frequency. This follow-up widens the public footprint to four signals: Wikipedia pageviews, Wikidata sitelinks, domain age and GDELT media mentions.

---

# Research Question

Does a broader public footprint explain AI recommendation frequency better than Wikipedia fame alone?

---

# Experimental Setup

- Model: gpt-4o
- Temperature: 0.7
- Closed-book baseline reused from Cold Start, no new model calls
- 95 distinct brands
- 4 public footprint signals per brand
- ~380 free public API/WHOIS lookups
- 50 brands with all four signals present
- Multiple regression with bootstrap analysis

---

# Key Findings

- Wikipedia pageviews alone: R² 2.3%, p=0.135.
- Wikidata sitelinks: R² 0.9%, p=0.365.
- Domain age: R² 2.2%, p=0.147.
- GDELT media mentions: R² 5.2%, p=0.095.
- All four combined: R² 11.2%.
- A stricter 75-brand cut produced a combined R² of 6.1%.
- All footprint signals remain far below the 61.4% self-consistency benchmark.

---

# Why It Matters

Broadening the public footprint from one fame proxy to four signals increases explanatory power somewhat, but not enough to approach the model's own historical recommendation behavior. The result narrows the plausible explanation for recommendation memory without identifying its source.

---

# Dataset

- 95 distinct brands
- 4 public footprint signals
- 50 brands with complete data
- ~380 public API/WHOIS lookups
- Closed-book recommendation frequency reused from Cold Start

---

# Methodology

The study reused the closed-book recommendation baseline from Cold Start. For each distinct brand, four free public signals were collected: 12-month Wikipedia pageviews, Wikidata sitelinks, domain age in days, and 12-month GDELT media mention volume capped at 250 records. Individual correlations/regressions were tested against recommendation frequency, then all four signals were combined for a multiple regression on the 50 brands with complete data. Cluster bootstrap confidence intervals and significance tests were used. A stricter 75-brand inclusion threshold was also evaluated.

For the study-specific implementation details see:

`methodology.md`

---

# Related Research

- The Fame Study
- The Model Predicts Itself
- We Invented a Brand With Zero History. Reviews Got It Picked Anyway
- Candidacy vs Selection

---

# Resources

- `Charts/individual-signals.svg`
- `Charts/r2-comparison.svg`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

Broadening the public footprint from one fame proxy to four signals increases explanatory power somewhat, but not enough to approach the model's own historical recommendation behavior. The result narrows the plausible explanation for recommendation memory without identifying its source.

Full write-up: https://atomfoundry.dev/research/memory-source

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
