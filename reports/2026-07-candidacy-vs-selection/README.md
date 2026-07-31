# Candidacy vs Selection

Recommendation Intelligence Research™ · Atom Foundry · July 2026

---

# Research Summary

Previous studies measured recommendation frequency only among brands already recommended by AI.

This study removes that restriction.

Across 60,924 ecommerce stores, we asked a more fundamental question:

What separates stores that are ever recommended from those that are never recommended?

The answer is not overall store quality.

It is intent.

---

# Research Question

Does store quality determine whether a store is recommended, or only whether it becomes eligible for recommendation?

---

# Experimental Setup

- AI Model: GPT-4o
- 60,924 ecommerce stores
- 599 recommended
- 60,325 never recommended
- Seven AI Commerce Score components evaluated

---

# Key Findings

- Recommended stores averaged 55.4 AI Commerce Score.
- Never-recommended stores averaged 56.0.
- Overall store quality showed virtually no difference.
- Intent scores were approximately 39% higher among recommended stores.
- Once a store entered the recommendation set, intent explained only 1.2% of recommendation frequency.

---

# Why It Matters

Recommendation systems appear to operate in two stages.

The first stage determines whether a store becomes a recommendation candidate.

The second determines which candidate is ultimately selected.

Store quality contributes to candidacy.

It contributes very little to selection.

This distinction explains why previous studies found almost no relationship between store quality and recommendation frequency despite measurable differences in intent.

---

# Dataset

The published dataset includes:

- Population comparison
- AI Commerce Score
- Seven score components
- Intent analysis
- Robustness validation

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
- Search Changes the Vocabulary
- AI Confabulates Its Reasons

---

# Resources

- `Charts/`
- `experiment-summary.csv`
- `component-comparison.csv`
- `methodology.md`

---

# Conclusion

Recommendation candidacy and recommendation selection are different processes.

Store quality helps determine whether a business enters the recommendation pool.

Once inside that pool, however, recommendation frequency is driven largely by factors outside the measurable dimensions of overall store quality.

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
