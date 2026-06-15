# Methodology

## Research Objective

Measure whether AI recommendation frequency is related to AI Commerce Score™ across multiple ecommerce categories.

The study combines five independent Recommendation Intelligence™ datasets into a single cross-category analysis.

## Dataset

* Categories: 5
* Model: GPT-4o-mini
* Shopping Intents: 100
* Runs Per Intent: 20
* Prompt Runs: 2,000
* Recommendations Captured: 20,000
* Distinct Brands Observed: 1,490

Categories Included:

* Beauty
* Supplements
* Coffee
* Pets
* Home & Living

## Metrics

### Recommendation Share™

Percentage of all recommendations captured by a brand.

### Recommendation Frequency™

Percentage of prompt runs in which a brand appeared at least once.

### Recommendation Position™

Average position within the AI response when the brand appeared.

### AI Commerce Score™

Atom Foundry's proprietary measure of store AI readiness.

The score evaluates machine readability, machine understanding, trust signals, and overall AI accessibility.

## Data Processing

Recommendations were collected from repeated AI shopping prompts.

Retailers and marketplaces were separated from single-brand stores and excluded from brand-level correlation analysis.

Brands were mapped to real stores where a verified match existed.

Brands without a verified store match were reported as off-index.

## Statistical Analysis

Pearson correlation was calculated between Recommendation Frequency™ and AI Commerce Score™ within each category.

Results:

| Category      |      r |
| ------------- | -----: |
| Beauty        |  0.170 |
| Supplements   | -0.015 |
| Coffee        |  0.019 |
| Pets          | -0.366 |
| Home & Living |  0.108 |

## Key Observation

No category produced a meaningful positive relationship between Recommendation Frequency™ and AI Commerce Score™.

The strongest relationship observed was Pets, where recommendation frequency showed a weak negative relationship with store readiness.

## Limitations

* Single AI model
* Single point in time
* Correlation does not imply causation
* Recommendation systems evolve continuously
* Results reflect observed recommendation behavior rather than underlying model architecture

All findings are based exclusively on captured recommendation data.
