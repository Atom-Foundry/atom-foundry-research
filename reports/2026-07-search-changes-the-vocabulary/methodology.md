# Methodology

This study follows the standard Atom Foundry Research Methodology.

For the complete research framework, see:

`/METHODOLOGY.md`

---

# Objective

Measure how enabling web search changes the vocabulary AI uses when describing recommended ecommerce products and brands.

---

# Research Question

Does web search change only which brands are recommended, or does it also change the language the model uses to describe them?

---

# Experimental Design

The same 50 buyer-intent prompts were executed twice:

- Search Off
- Search On

Categories, prompts and evaluation procedure remained identical.

Only web search availability changed.

---

# Dataset

- AI Model: GPT-4o
- Prompts: 50
- Conditions: Search On vs Search Off

---

# Evaluation

Responses from both conditions were tokenized and compared using normalized word-frequency ratios.

The analysis identified the words with the largest relative frequency increase after web search was enabled.

---

# Metrics

Primary metrics included:

- Normalized Word-Frequency Ratio
- Largest Word Shift
- Search-On Noise Floor
- Search-Off Noise Floor

---

# Limitations

The published visualization highlights only the strongest vocabulary shifts.

It is not intended to represent every word that changed between conditions.

---

Published by Atom Foundry

AI Commerce Intelligence™
