# Two Months Later, the Model Still Agrees With Itself

Recommendation Intelligence Research™ · Atom Foundry · August 2026

---

# Research Summary

The Model Predicts Itself showed that June's recommendation position predicts July's at R² 61.4% and that the ranking did not move across a 15-day window. This follow-up asks whether the same stability survives six independently triggered runs across two full months.

---

# Research Question

Does the model's #1 recommendation hold over two months of independent, repeated sampling?

---

# Experimental Setup

- Model: gpt-4o-mini
- Temperature: 0.7
- 50 shopping intents across 10 categories
- 6 independent sweeps, June 30–August 26 2026
- 10 runs per intent per sweep
- 30,170 recommendations analyzed
- Concordance rule: exact same #1 brand in every sweep
- 7 non-concordant intents received a 20-run same-day confirmatory check

---

# Key Findings

- 43 of 50 intents (86%) returned the exact same #1 brand in every sweep.
- 7 of 50 intents (14%) changed #1 at least once.
- Two of the three borderline cases tested at 20 runs resolved as sampling noise.
- Ceramic dinnerware remained a genuine split: Fiesta 50%, Corelle 40% at 20 runs.
- Category specialists averaged position 1.6 versus 7.4 for broad generalist retailers in the supporting comparison.

---

# Why It Matters

Most categories appear to be structurally settled. For locked intents, daily monitoring buys little because there is little movement to catch. The contested minority is different: those are the categories where a change in content or product evidence has somewhere real to land.

---

# Dataset

- 50 shopping intents
- 10 ecommerce categories
- 6 independent sweeps
- 30,170 recommendations
- 20-run confirmatory checks for three borderline intents

---

# Methodology

The same 50 intents were submitted repeatedly to gpt-4o-mini at temperature 0.7. Each sweep contained ten runs per intent. Six sweeps were collected over 58 days. The primary outcome was binary: whether the exact same brand occupied position #1 in every sweep. Three borderline cases were re-run at 20 samples to separate persistent disagreement from small-sample noise. Two sweep identifiers were corrected after tracing execution timestamps and splitting a duplicated same-day identifier.

For the study-specific implementation details see:

`methodology.md`

---

# Related Research

- The Model Predicts Itself
- Hand It a Rating, and It Follows Every Single Time
- The State of AI Recommendations Across Commerce 2026

---

# Resources

- `Charts/locked-intents.svg`
- `Charts/borderline-intents.svg`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

Most categories appear to be structurally settled. For locked intents, daily monitoring buys little because there is little movement to catch. The contested minority is different: those are the categories where a change in content or product evidence has somewhere real to land.

Full write-up: https://atomfoundry.dev/research/recommendation-lock-in

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
