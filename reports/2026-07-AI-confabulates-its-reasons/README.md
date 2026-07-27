# AI Confabulates Its Reasons

Recommendation Intelligence Research™ · Atom Foundry · July 2026

---

# Research Summary

Do AI systems repeatedly reuse the same recommendation explanations, or do they generate new reasoning every time?

This study analyzed 29,633 recommendation explanations produced throughout the Atom Foundry research program.

The results show that explanation reuse is remarkably rare.

Approximately 90% of all explanations appeared only once in the entire dataset.

---

# Research Question

How often do AI systems reuse the same recommendation explanation?

---

# Experimental Setup

- AI Model: GPT-4o
- Recommendation explanations analyzed: 29,633
- Distinct explanations: 26,812
- Evaluation method: Exact-text matching

Every explanation was compared against every other explanation to identify repeated reasoning.

---

# Key Findings

- 29,633 explanations analyzed
- 26,812 unique explanations
- 90% uniqueness rate
- Only 10% of explanations appeared more than once
- The single most repeated explanation appeared only 12 times

---

# Why It Matters

AI explanations are not generated from a small library of reusable templates.

Instead, the model produces highly diverse explanations, even when recommendation behavior appears similar.

This suggests that explanation generation is itself a generative process rather than simple retrieval of predefined responses.

---

# Dataset

The published dataset summarizes:

- Explanation uniqueness
- Duplicate explanations
- Distinct explanations
- Maximum repetition frequency

---

# Methodology

This study follows the standard Atom Foundry Research Methodology.

For the complete methodology see:

`/METHODOLOGY.md`

Study-specific implementation details are documented in `methodology.md`.

---

# Related Research

- The State of AI Recommendations Across Commerce 2026
- Web Search Changes AI Recommendations
- AI Knows Your Website
- The Model Predicts Itself

---

# Resources

- `Charts/`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

Recommendation explanations are overwhelmingly unique.

Rather than repeating fixed templates, AI systems generate new natural-language explanations for nearly every recommendation they produce.

Understanding this distinction is essential when interpreting AI-generated reasoning in ecommerce recommendations.

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
