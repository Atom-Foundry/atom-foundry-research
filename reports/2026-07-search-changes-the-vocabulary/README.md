# Search Changes the Vocabulary

Recommendation Intelligence Research™ · Atom Foundry · July 2026

---

# Research Summary

Does web search change only which brands AI recommends, or does it also change how the model talks about them?

This study compares recommendation language generated with web search disabled and enabled using identical buyer-intent prompts.

The results show that enabling search substantially shifts the vocabulary toward concrete, product-specific terminology.

---

# Research Question

How does web search affect the language AI uses in ecommerce recommendations?

---

# Experimental Setup

- AI Model: GPT-4o
- 50 identical buyer-intent prompts
- Search Off
- Search On
- Normalized word-frequency analysis

Only search availability changed.

---

# Key Findings

- The largest vocabulary shift reached 21×.
- Words such as *monohydrate*, *whey*, *creatine*, *collagen* and *third party* became dramatically more common with search enabled.
- Nearly all of the strongest shifts involved ingredients, specifications or measurable product characteristics.
- General brand-impression language became relatively less dominant.

---

# Why It Matters

Retrieval changes more than recommendation selection.

It changes the evidence the model chooses to communicate.

When search is available, AI increasingly grounds its recommendations in observable product attributes rather than broad marketing language.

This distinction improves transparency and makes factual verification easier.

---

# Dataset

The published dataset summarizes:

- Search On vocabulary
- Search Off vocabulary
- Relative word-frequency shifts
- Largest vocabulary changes

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
- AI Confabulates Its Reasons

---

# Resources

- `Charts/`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

Web search changes not only what AI recommends but also how those recommendations are expressed.

The language shifts toward concrete, verifiable product characteristics, suggesting that retrieval influences both recommendation selection and explanation quality.

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
