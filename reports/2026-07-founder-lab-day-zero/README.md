# Founder Lab · Day Zero

Founder Lab · July 2026

---

# Research Summary

Founder Lab is Atom Foundry's own ecommerce laboratory.

Before changing a single line of copy, schema or technical implementation, we measured exactly where the store starts.

The baseline AI Commerce Score is **78/100**.

Across six scans of an unchanged website the score varied only between **76 and 78**, with every deterministic component remaining identical.

Only the Intent score moved.

---

# Research Question

How stable is the AI Commerce Score before any optimization begins?

---

# Experimental Setup

- Shopify store
- Six independent scans
- Five rescans within 62 seconds
- No website changes
- AI Commerce Score evaluation
- AI bot instrumentation

---

# Key Findings

- Baseline score: **78**
- Six scans ranged from **76–78**
- Every deterministic score component remained identical
- Only Intent changed
- Technical score was the weakest deterministic component (7/15)
- No AI bot visits were recorded

---

# Why It Matters

Before improving a measurement system, its natural variability must be understood.

This baseline establishes the practical noise floor of the AI Commerce Score.

Changes smaller than the observed baseline variation should not automatically be interpreted as meaningful improvements.

Founder Lab now becomes the controlled environment used to validate future Recommendation Intelligence research under real commercial conditions.

---

# Dataset

The published dataset includes:

- Six baseline scans
- Component-level scores
- AI Commerce Score
- Technical readiness
- AI bot instrumentation status

---

# Methodology

This study follows the standard Atom Foundry Research Methodology.

Implementation details are documented in `methodology.md`.

---

# Related Research

- The State of AI Recommendations Across Commerce
- Search Changes AI Recommendations
- Candidacy vs Selection
- The Strongest Signal We Have

---

# Resources

- `Charts/`
- `experiment-summary.csv`
- `baseline-scans.csv`
- `methodology.md`

---

# Conclusion

Founder Lab begins with an AI Commerce Score of **78/100**.

The first experiment demonstrated that deterministic website measurements remain perfectly stable across repeated scans while small variation originates entirely from the model-evaluated Intent component.

This baseline provides the reference point for every optimization experiment that follows.

---

Published by **Atom Foundry**

Founder Lab — the controlled laboratory for AI Commerce Intelligence™.
