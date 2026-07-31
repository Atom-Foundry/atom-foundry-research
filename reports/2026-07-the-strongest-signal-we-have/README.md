# The Strongest Signal We Have

Recommendation Intelligence Research™ · Atom Foundry · July 2026

---

# Research Summary

What best predicts which brands AI will recommend?

This study compares four independent external signals against one internal signal derived from the model's own historical recommendation behavior.

Store quality, public fame, web visibility and intent all explain almost none of the variation in recommendation frequency.

The strongest predictor is the model's own previous output.

Across a month, separate datasets and a model update, recommendation position remained highly predictable.

---

# Research Question

What is the strongest measurable predictor of AI recommendation behavior?

---

# Experimental Setup

- AI Model: GPT-4o
- 1,082 brand-intent pairs
- June vs July comparison
- Same 50 buyer intents
- Pearson correlation analysis
- Separate collection runs

---

# Key Findings

- Position in June predicts position in July with an R² of **61.4%**.
- Recommendation frequency predicts future frequency with an R² of **54.4%**.
- Position predicts future frequency with an R² of **31.9%**.
- Store quality explains only **0.7%** of recommendation frequency.
- Public fame explains **1.2%**.
- Web traces explain **0.2%**.
- Intent explains **1.2%** once brands are already recommended.
- Recommendation drift remained effectively unchanged across 15 days.

---

# Why It Matters

The strongest measurable signal is not an external property of the brand.

It is the model's own previous recommendation behavior.

This suggests recommendation systems maintain highly stable internal preference structures over time.

For merchants, this means recommendation behavior changes far more slowly than commonly assumed.

For researchers, it suggests that historical recommendation data contains substantial predictive value.

---

# Dataset

The published dataset includes:

- Month-to-month recommendation stability
- External signal comparison
- Recommendation drift analysis
- Supporting validation measurements

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
- Web Search Changes AI Recommendations
- Search Changes the Vocabulary
- AI Knows Your Website

---

# Resources

- `Charts/`
- `experiment-summary.csv`
- `external-signals.csv`
- `methodology.md`

---

# Conclusion

Historical recommendation behavior explains future recommendation behavior substantially better than any external characteristic measured in this research.

Recommendation systems appear to exhibit stable internal structures that persist across time, separate data collection runs and even model updates.

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
