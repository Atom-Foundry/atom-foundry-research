# The Fame Study

Recommendation Intelligence Research™ · Atom Foundry · June 2026  
**Corrected 17 July 2026**

---

# Research Summary

Does public fame explain why AI repeatedly recommends certain brands?

Our original publication concluded that public fame explained substantially more recommendation frequency than ecommerce store quality.

That conclusion was incorrect.

After rebuilding the brand-to-store mapping and repeating the identical regression on 872 correctly matched brands, the apparent fame effect disappeared.

Neither store quality nor our measured fame signals explained recommendation frequency beyond the level expected from random variation.

One result, however, remained completely unchanged.

Recommendation stability.

---

# Research Question

Does measurable public fame predict AI recommendation frequency?

---

# Experimental Setup

- AI Model: GPT-4o-mini
- 872 corrected commercial brands
- 20 recommendation runs per intent
- Multiple regression
- Adjusted R²
- Permuted-null comparison

---

# Key Findings

- Store quality explains **0.7%** of recommendation frequency.
- Public fame explains **1.2%**.
- Randomly shuffled data explains **1.2%**.
- The previously reported **24.9%** fame effect was caused by an incorrect brand-to-store join.
- Recommendation stability remained between **78% and 91%** across categories and was unaffected by the correction.

---

# Why It Matters

Correcting mistakes is part of scientific research.

The correction removes the evidence that public fame predicts recommendation frequency.

At the same time, it strengthens a more interesting observation.

Recommendation behavior remains remarkably stable despite neither measurable store quality nor measurable public fame explaining why particular brands consistently win.

This shifts the research focus away from external brand characteristics and toward the internal dynamics of recommendation systems.

---

# Dataset

The published dataset includes:

- Corrected regression analysis
- Recommendation stability
- Fame signal comparison
- Permuted-null evaluation

---

# Methodology

This study follows the standard Atom Foundry Research Methodology.

For the complete methodology see:

`/METHODOLOGY.md`

Study-specific implementation details are documented in `methodology.md`.

---

# Related Research

- The State of AI Recommendations Across Commerce 2026
- Candidacy vs Selection
- The Strongest Signal We Have
- Web Search Changes AI Recommendations

---

# Resources

- `Charts/`
- `experiment-summary.csv`
- `regression-results.csv`
- `methodology.md`

---

# Conclusion

The corrected analysis provides no evidence that either measured store quality or measured public fame explains AI recommendation frequency.

What remains is a stable recommendation system whose behavior is reproducible but largely unexplained by the external variables examined in this research.

Understanding those hidden drivers remains one of the central open questions of Recommendation Intelligence™.

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
