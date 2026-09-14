# The Model Is Almost Never Wrong About Your Brand. It Just Doesn't Say Much.

**Atom Foundry · Recommendation Intelligence Research™ · Study #27**

Published: September 11, 2026

[![DOI](https://zenodo.org/badge/1266113982.svg)](https://doi.org/10.5281/zenodo.22754000)

---

## The short version

We tested what happens when an AI model is asked what it knows about a brand without being given a specific question or topic.

The model was highly accurate about the information it chose to provide.

But accuracy was not the main problem.

The bigger problem was **depth**.

Across 9 e-commerce brands, we collected 40 claims from the model:

- **34** were factual and checkable
- **6** were descriptive or stylistic
- **33 of 34** checkable claims were confirmed
- **1 of 34** was contradicted
- **97.1%** of checkable claims were accurate
- Yet the model covered only **44 of 72 possible brand-topic combinations**
- **61.1%** of the available topic space was covered

In other words:

The model was almost always right about what it said.

It simply did not say very much.

---

## The two metrics

### Brand Accuracy Score (BAS)

BAS measures whether the factual claims the model volunteered about a brand were correct.

**BAS = confirmed checkable claims / total checkable claims × 100**

Across the study:

**33 / 34 = 97.1%**

This is a measure of **accuracy**, not completeness.

---

### Coverage Depth Index (CDI)

CDI measures how much of the predefined attribute space the model covered without being explicitly prompted for individual topics.

We defined 8 attribute categories across 9 brands:

1. Materials
2. Pricing / Positioning
3. Sustainability / Ethics
4. Design / Functionality
5. Warranty / Returns
6. Certifications / Awards
7. Business Model / Distribution
8. Competitor Comparison

That creates:

**9 brands × 8 categories = 72 possible brand-category pairs**

The model covered:

**44 / 72 = 61.1%**

This means the model was accurate about the information it volunteered, but left a meaningful amount of the available brand context untouched.

---

## The brands

The study used the same 9 Wave-1 brands from the original collection:

- Bellroy
- Boll & Branch
- Branch
- Caraway
- Onyx Coffee Lab
- Peak Design
- Rumpl
- Wild One
- Zigpoll

The original collection was performed using `gpt-4o`.

No new API calls were made for this study.

---

## Brand Accuracy Score

| Brand | Checkable Claims | Confirmed | BAS |
|---|---:|---:|---:|
| Bellroy | 4 | 3 | 75.0% |
| Boll & Branch | 4 | 4 | 100.0% |
| Branch | 4 | 4 | 100.0% |
| Caraway | 3 | 3 | 100.0% |
| Onyx Coffee Lab | 4 | 4 | 100.0% |
| Peak Design | 5 | 5 | 100.0% |
| Rumpl | 3 | 3 | 100.0% |
| Wild One | 4 | 4 | 100.0% |
| Zigpoll | 3 | 3 | 100.0% |

The only contradicted checkable claim was related to Bellroy pricing.

The model described Bellroy as cheaper than Peak Design and Nomatic.

The Peak Design comparison was close, but the Nomatic comparison was not supported.

---

## Coverage Depth Index

| Brand | Covered Categories | Possible | CDI |
|---|---:|---:|---:|
| Bellroy | 7 | 8 | 87.5% |
| Boll & Branch | 6 | 8 | 75.0% |
| Wild One | 6 | 8 | 75.0% |
| Branch | 6 | 8 | 75.0% |
| Peak Design | 5 | 8 | 62.5% |
| Rumpl | 5 | 8 | 62.5% |
| Onyx Coffee Lab | 4 | 8 | 50.0% |
| Caraway | 3 | 8 | 37.5% |
| Zigpoll | 2 | 8 | 25.0% |

---

## Category coverage

| Category | Brands Covered | Coverage |
|---|---:|---:|
| Sustainability / Ethics | 8 / 9 | 88.9% |
| Materials | 7 / 9 | 77.8% |
| Pricing / Positioning | 7 / 9 | 77.8% |
| Design / Functionality | 7 / 9 | 77.8% |
| Competitor Comparison | 5 / 9 | 55.6% |
| Business Model / Distribution | 4 / 9 | 44.4% |
| Warranty / Returns | 3 / 9 | 33.3% |
| Certifications / Awards | 3 / 9 | 33.3% |

The model was most likely to volunteer information about sustainability, materials, pricing and design.

It was much less likely to volunteer warranty, returns, certifications and business-model information.

---

## What this tells us

The result creates an important distinction between **accuracy** and **depth**.

A brand can be represented accurately while still being represented incompletely.

That matters for AI commerce because recommendation systems do not operate on a single fact.

They build an internal representation of brands and products from the information available to them.

If some dimensions are consistently missing, the model may still be factually correct while having an incomplete picture of the brand.

That creates a different problem from hallucination.

It is not:

**"AI is wrong about my brand."**

It can be:

**"AI is right about my brand, but it doesn't know enough about it."**

---

## What we measured

The study measures two different properties:

### Accuracy

When the model made a checkable factual claim, was that claim supported by independent sources?

### Depth

Across the predefined attribute taxonomy, how many brand-topic combinations did the model cover without being explicitly prompted for each topic?

These should not be treated as the same metric.

A model can have very high accuracy and relatively low depth.

That is exactly what we observed here.

---

## Data boundary

This study uses the claims and aggregate results published in the original research.

There were **0 new API calls** for this verification study.

The study does not claim to provide a complete raw claim-level audit trail for every model response.

---

## Limitations

- The study covers 9 brands.
- The taxonomy of 8 categories was defined by Atom Foundry.
- CDI measures topic coverage, not factual truth.
- BAS only includes checkable factual claims.
- Descriptive or stylistic claims were excluded from BAS but included in CDI.
- Web search can miss information.
- Prices were spot-checked against available sources.
- Independent verification relied on brand websites, independent press, retailers and review sources.
- A single researcher performed the verification.
- Correlation or coverage does not establish causation.

---

## The takeaway

The model was not struggling primarily with factual accuracy.

It was struggling with **what it chose to surface**.

That distinction matters.

Because the next question is not only:

**Does AI know your brand?**

It is:

**What does AI know about your brand, what does it leave out, and which parts of that representation matter when it has to choose?**

---

## Source

Atom Foundry  
Recommendation Intelligence Research™

Study #27 · September 11, 2026

https://atomfoundry.dev/research/accuracy-depth
