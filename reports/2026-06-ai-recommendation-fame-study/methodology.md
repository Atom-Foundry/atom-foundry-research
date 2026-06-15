# Methodology

## Research Objective

Measure whether public fame signals explain AI recommendation behavior better than store-level AI readiness.

## Dataset

* Brands Analyzed: 200
* Categories Included: 5
* Recommendation Dataset: 20,000 recommendations
* Model: GPT-4o-mini
* Shopping Intents: 100
* Runs Per Intent: 20

Categories:

* Beauty
* Supplements
* Coffee
* Pets
* Home & Living

## Fame Signals

The following public signals were collected for each brand:

* Wikipedia pageviews
* Number of Wikipedia language editions
* Wikipedia article length
* Brand name length

These variables were used as observable proxies for public fame.

## Store Quality Variable

AI Commerce Score™

Atom Foundry's proprietary measure of store AI readiness.

## Statistical Analysis

Two models were evaluated.

### Model 1

Dependent Variable:

Recommendation Frequency™

Independent Variable:

AI Commerce Score™

Result:

R² = 0.021

### Model 2

Dependent Variable:

Recommendation Frequency™

Independent Variables:

* Wikipedia pageviews
* Wikipedia language editions
* Wikipedia article length
* Brand name length

Result:

R² = 0.249

## Additional Analysis

Top 50 versus Bottom 50 comparison

Metrics compared:

* AI Commerce Score™
* Wikipedia presence
* Wikipedia readership

Recommendation stability analysis

Measured:

* Top-1 recommendation consistency
* Brand-level variation across 20 runs

## Key Observation

Public fame signals explained approximately twelve times more recommendation behavior than AI Commerce Score™.

However, approximately three quarters of recommendation behavior remained unexplained.

## Limitations

* Fame measured using public proxy variables
* Wikipedia is not a complete measure of brand awareness
* Advertising exposure could not be reliably measured
* Forum and community exposure could not be reliably measured
* Results do not imply causation

All findings are based exclusively on captured recommendation data and publicly observable signals.
