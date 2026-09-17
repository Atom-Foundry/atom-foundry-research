# Methodology — PDP Specificity (Study #32)

## Research question

Does making brand language more concrete (vague marketing copy versus specific, PDP-pricing-page-style claims) change which brand an AI model recommends, and does that effect depend on the product category?

## Design

Three conditions per brand, with the underlying brand facts held fixed:

1. **No claims** (control) — approx. 19 words
2. **Vague** — generic marketing language, no numbers — approx. 37 words
3. **Specific** — concrete PDP/pricing-page style claims — approx. 47 words

**Rounds 1-2 (original 4 brands)**: Colored Organics (organic baby clothes, trust), BodyArtForms (body piercing jewelry, trust), Barbaro Mojo (Cuban-style hot sauce, functional), Hearthloom (ceramic dinnerware, functional). 4 brands x 3 conditions x 20 intents x 5 repeats = 1,200 calls per round, run twice as independent replications.

**Round 3 (4 new brands)**: 2 more trust-category brands (Wild One - dog gear, Primally Pure - natural deodorant) and 2 more functional-category brands (Bellroy - slim leather wallets, Zigpoll - Shopify survey tool), tested against fixed competitors (Ruffwear, Native Deodorant, Herschel, SurveyMonkey). Same 20 intents x 5 repeats structure, 1,200 fresh calls.

- Total: 3,600 calls across 3 rounds
- Model: GPT-4o throughout. Winner determination: GPT-4o LLM judge
- 0 parse failures across all 3,600 judge calls

## Statistics

- Two-proportion z-tests, chi-square tests across the 3 conditions (chi-square=780.09, df=2, p<0.0001 for the original pooled result)
- Logistic regression controlling for brand and word count: specificity remains significant (p=0.0005), word count alone is not (p=0.24) for rounds 1-2. In round 3, word count's own effect reached p=0.004, but specificity remained significant (p=0.007) controlling for word count.
- Brand x specificity interaction (rounds 1-2): chi-square=35.87, df=3, p<0.0001
- Category x specificity interaction (all 8 brands, controlling for brand, all 2,400 calls): chi-square=39.26, df=1, p<0.0001

## Results by brand (rounds 1-2 combined, n=200/brand/condition)

| Brand | Category | Vague | Specific | Change |
|---|---|---|---|---|
| Colored Organics | Trust | 93.5% | 85.0% | -8.5pp (p=0.006, reversed) |
| BodyArtForms | Trust | 9.0% | 10.0% | +1.0pp (p=0.73, flat) |
| Barbaro Mojo | Functional | 50.5% | 68.0% | +17.5pp (p<0.001) |
| Hearthloom | Functional | 63.5% | 88.5% | +25.0pp (p<0.001) |

## Results by brand (round 3, new brands)

| Brand | Category | Vague | Specific | Note |
|---|---|---|---|---|
| Wild One | Trust | 87.0% | 74.0% | p=0.020, reversed |
| Primally Pure | Trust | 99.0% | 100.0% | p=0.32, ceiling |
| Zigpoll | Functional | 85.0% | 96.0% | p=0.008 |
| Bellroy | Functional | 100.0% | 98.0% | p=0.16, ceiling |

Zero of the 4 trust-category brands showed specificity significantly helping; 3 of the 4 functional-category brands did.

## Pooled category result (all 8 brands, n=600/bar)

| Category | Vague | Specific | Change |
|---|---|---|---|
| Functional | 68.8% | 84.5% | +15.7pp (p<0.0001) |
| Trust | 65.2% | 60.7% | -4.5pp (p=0.11 alone, not significant at this sample) |

## Limitations

- One model (GPT-4o) and one system-message injection mechanism were tested; results may not generalize to other retrieval-augmented or web-search-enabled setups.
- The trust-versus-functional axis was tested with 2 brands per side per round, not an exhaustive category survey.
- 2 of the 4 round-3 brands (Bellroy, Primally Pure) were already so close to 100% that specificity had little room to move the number (ceiling effects).
- Most model responses, in every condition, picked some brand other than the target or its named competitor. This measures how much a given version of a brand's claims pulls selection toward that brand, not a clean two-way contest.
- Round 3's brands were already well-known, producing a 24.5% no-claims baseline versus 0.0% for the obscure rounds 1-2 brands — the category-by-specificity split, not any single round's baseline, is the number meant to generalize.
- A related, later study (Study #37, signal-hierarchy) found specificity to be the strongest single marginal contributor among four signals tested head-to-head.

## Data package note

`data.csv` in this package contains only the aggregate, published metrics shown on the live research page (https://atomfoundry.co/research/pdp-specificity.html). No row-level or per-call model responses are included, consistent with Atom Foundry's data-sharing practice for this research series.
