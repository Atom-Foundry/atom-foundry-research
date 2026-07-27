# Methodology

This study follows the standard Atom Foundry Research Methodology.

For the complete research framework, see:

`/METHODOLOGY.md`

---

# Objective

Measure whether AI systems generate genuinely new explanations for recommendations or repeatedly reuse the same reasoning across different recommendations.

---

# Research Question

Do AI systems produce original recommendation explanations, or do they rely on a limited library of repeated reasons?

---

# Experimental Design

Recommendation explanations were extracted from the complete recommendation dataset generated throughout the Atom Foundry research program.

Every explanation was compared using exact-text matching to identify duplicated reasoning.

---

# Dataset

- AI Model: GPT-4o
- Recommendation explanations analyzed: 29,633
- Distinct explanations: 26,812

---

# Evaluation

Every explanation was normalized and compared against every other explanation.

The analysis measured:

- Exact duplicate explanations
- Unique explanations
- Explanation reuse frequency
- Maximum repetition count

Paraphrases were intentionally treated as different explanations.

---

# Metrics

Primary metrics included:

- Explanation Uniqueness Rate
- Duplicate Explanation Rate
- Distinct Explanation Count
- Maximum Repetition Frequency

---

# Limitations

The analysis measures exact-text repetition only.

Two explanations expressing the same idea with different wording are considered unique.

As a result, the measured uniqueness rate represents a conservative lower bound.

---

Published by Atom Foundry

AI Commerce Intelligence™
