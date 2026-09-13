# Methodology

## Study

**Title:** The Model Is Almost Never Wrong About Your Brand. It Just Doesn't Say Much.

**Study:** #27

**Series:** Recommendation Intelligence Research™

**Published:** 2026-09-11

**Source:** https://atomfoundry.dev/research/accuracy-depth

## Design

The study reuses the closed-book possession claims from **Possession vs Deployment**.

- Brands: 9 Wave-1 brands
- Model: gpt-4o
- Original collection: 3 runs merged to stable claims
- New model/API calls for this study: 0
- Claims reused: 40
- Factual/checkable claims: 34
- Purely descriptive claims: 6
- Attribute taxonomy: 8 categories

The new work was independent verification and classification. Each claim was checked through live web search against the brand's own site, independent press, retailers, or review sources. The same model that produced the claim did not grade its own claim.

## Brand Accuracy Score (BAS)

BAS measures the share of checkable factual claims that were independently confirmed.

**Formula:**

`BAS = confirmed checkable claims / total checkable claims × 100`

Only falsifiable factual claims are included. Six purely descriptive claims were excluded from BAS because descriptions such as "minimalist" or "vibrant" do not have a clear true/false test in this design.

Overall:

`33 confirmed / 34 checkable = 97.1%`

## Content Depth Index (CDI)

CDI measures topic breadth, not truth.

Each brand was evaluated across eight attribute categories:

1. Materials
2. Pricing / Positioning
3. Sustainability / Ethics
4. Design / Functionality
5. Warranty / Returns
6. Certifications / Awards
7. Business Model / Distribution
8. Competitor Comparison

There are `9 brands × 8 categories = 72` possible category-brand pairs.

The model touched 44 of those pairs.

**Formula:**

`CDI = category-brand pairs covered / total possible category-brand pairs × 100`

`44 / 72 = 61.1%`

The taxonomy was applied to the claims and descriptions produced in the original possession dataset. A category counts as covered when the unprompted description touched that attribute area.

## Independent verification

The verification was intentionally external to the generating model. Claims were checked against real sources including:

- Brand-owned websites
- Independent press
- Retailers
- Review sources

One important quality-control correction occurred during verification. An earlier, less rigorous pass had flagged an Onyx Coffee Lab sustainability claim as suspicious. Source-by-source re-verification supported the claim. The actual contradiction was a Bellroy pricing comparison involving Nomatic.

## Bellroy pricing miss

The contradicted claim stated that Bellroy pricing was lower than Peak Design and Nomatic.

The spot-check found:

- Bellroy Slim Sleeve: $85–135
- Nomatic flagship wallet: $19.99

The Nomatic comparison therefore did not hold. Peak Design's comparable Passport Wallet was close to Bellroy's range.

## Interpretation

The study separates two concepts that are easy to conflate:

**Accuracy:** Is the information the model volunteers correct?

**Depth:** How much relevant, real information does the model volunteer at all?

The result is high accuracy with incomplete and uneven coverage. In this cohort, the model was usually right about what it said. It was selective about which parts of a brand it talked about.

## Limitations

1. The 8-category taxonomy is an Atom Foundry construction. Another reasonable taxonomy could change CDI without changing the underlying facts.
2. Verification was performed by a single researcher. No inter-rater reliability statistic was calculated.
3. Web search can miss information that is private, unindexed, or too recent to appear in search results.
4. Comparative pricing was spot-checked at a point in time, not continuously tracked.
5. The sample contains only 9 brands, so it is not large enough for a statistically powered BAS-to-CDI relationship.
6. Descriptive claims were excluded from BAS but retained for CDI by design.
7. CDI measures whether a topic was touched, not whether the information in that topic was accurate.

## Data boundary

This repository package contains aggregate results supported by the published research page. It does not reconstruct the original 40 claim-level records or invent source-level observations that are not presented in the study.
