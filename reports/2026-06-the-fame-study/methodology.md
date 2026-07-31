# Methodology

This study follows the standard Atom Foundry Research Methodology.

For the complete research framework, see:

`/METHODOLOGY.md`

---

# Objective

Evaluate whether measurable public fame explains AI recommendation frequency better than ecommerce store quality.

Following publication, the analysis was independently re-measured after discovering a data-processing error in the original brand-to-store mapping.

---

# Research Question

Do public fame signals predict AI recommendations once the dataset is correctly reconstructed?

---

# Experimental Design

Recommendation frequency from the Recommendation Intelligence dataset was compared against two groups of explanatory variables:

- AI Commerce Score
- Public fame signals

The original regression used 87 matched brands.

After identifying an error in the matching pipeline, the analysis was repeated on 872 correctly matched commercial brands using the identical regression model.

---

# Dataset

- AI Model: GPT-4o-mini
- Recommendation runs: 20 per intent
- Corrected brands: 872
- Original sample: 87

Public fame signals included:

- Wikipedia page views
- Language editions
- Article length
- Brand name length

Commercial entities were matched using Wikidata.

---

# Evaluation

Multiple linear regression was performed using identical predictors before and after rebuilding the brand-to-store mapping.

To estimate the level of random explanatory power expected from the same dataset, a permuted-null regression was also computed.

Recommendation stability was evaluated independently from the recommendation runs and was unaffected by the matching correction.

---

# Metrics

Primary metrics included:

- R²
- Adjusted R²
- Permuted Null R²
- Recommendation Stability

---

# Validation

The corrected regression increased the usable sample from 87 to 872 brands while preserving the original methodology.

Comparison against the permuted-null distribution demonstrated that the corrected fame effect is statistically indistinguishable from random variation.

---

# Limitations

Wikipedia is an imperfect proxy for commercial fame.

The study evaluates only publicly measurable fame signals and does not include advertising exposure, review ecosystems or proprietary engagement data.

The Top-50 vs Bottom-50 comparison still contains observations originating from the original matching pipeline and is therefore retained only as contextual evidence rather than a primary result.

---

Published by Atom Foundry

AI Commerce Intelligence™
