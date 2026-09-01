# Hand It a Rating, and It Follows Every Single Time

Recommendation Intelligence Research™ · Atom Foundry · August 2026

---

# Research Summary

How AI Decides flags Evaluation as the open gap: once two brands are genuinely close, what tips the final call? This study injects one comparison fact at a time into 16 real contested pairs.

---

# Research Question

What tips the model's verdict when two brands are genuinely close?

---

# Experimental Setup

- Model: gpt-4o
- Temperature: 0.7
- 50 open shopping intents across 10 categories
- 16 genuinely contested brand pairs after Phase 1
- Phase 2: 16 pairs × 10 no-data baseline runs = 160
- Phase 3: 16 pairs × 3 signals × 10 runs = 480
- 1,140 total model calls

---

# Key Findings

- A better rating + review count was followed in 160/160 runs (100%).
- A deeper spec list was followed in 81.9% of runs.
- Better price + availability was followed in 60.6% of runs.
- Against the paired no-data baseline, rating flipped 50.0% of runs (p<0.0001), specs 41.9% (p=0.0004), price 26.9% (p=0.055).
- Rating beat price by 23.1 percentage points in a Bonferroni-adjusted pairwise test (p=0.0012).
- The paired no-data noise floor was 11.2%.

---

# Why It Matters

Evaluation is not evenly weighted. In this controlled setting, review/rating evidence was the strongest lever, specifications were meaningful but smaller, and price/availability was the weakest of the three tested signals.

---

# Dataset

- 50 open prompts
- 16 genuine contested pairs
- 3 injected comparison signals
- 1,140 model calls
- 480 Phase 3 comparison runs

---

# Methodology

Phase 1 used 50 open prompts with ten runs each to identify contests where the top two brands were within four wins of one another. Two apparent contests were removed because the two names were actually the same brand or sub-brand. Phase 2 established a paired no-data baseline for the remaining 16 pairs. Phase 3 repeated each pair with one injected fact block at a time: price/availability, rating/review count, or specification depth. Results were evaluated as both raw follow-the-better-number rates and flip rates relative to the paired baseline, with cluster bootstrap intervals and permutation tests.

For the study-specific implementation details see:

`methodology.md`

---

# Related Research

- How AI Decides
- The Model Predicts Itself
- The Model Hedges Most When It’s Most Sure
- Two Months Later, the Model Still Agrees With Itself

---

# Resources

- `Charts/follow-better-number.svg`
- `Charts/flip-rate-vs-baseline.svg`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

Evaluation is not evenly weighted. In this controlled setting, review/rating evidence was the strongest lever, specifications were meaningful but smaller, and price/availability was the weakest of the three tested signals.

Full write-up: https://atomfoundry.dev/research/candidate-evaluation

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
