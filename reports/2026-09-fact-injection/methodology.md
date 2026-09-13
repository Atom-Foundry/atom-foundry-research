# Methodology

## Study

**Title:** Give the Model the One Fact It's Missing. The Brand Goes From Invisible to Everywhere.

**Study:** #25

**Series:** Recommendation Intelligence Research™

**Published:** 2026-09-08

**Source:** https://atomfoundry.dev/research/fact-injection

## Research question

Does directly injecting one real, verified fact about an underperforming brand change whether the brand gets mentioned in AI-generated shopping answers?

This study is the causal follow-up to **Possession vs Deployment**.

## Model

- Model: **gpt-4o throughout**
- Category: consumer ecommerce
- Brands: 4 deliberately selected underperformers
- Buyer prompts: 20 per brand
- Repeats: 10 per prompt in the injected condition

## Baseline

The baseline is reused from the already-published Recommendation Reports.

For each brand, the same published 20-prompt buyer-question set is used.

The baseline is not regenerated for this study.

The published baseline mention/recommendation rates for the four selected brands range from **0% to 16.5%**.

## Injected condition

For each brand:

1. Select one real, verified and distinctive fact.
2. Inject that fact into the system message.
3. Frame the message as retrieved context.
4. Ask the brand's existing real buyer questions without modification.
5. Detect whether the brand appears in the response.
6. On a capped sample of mentioned cells, score whether the specific fact is cited or clearly paraphrased.

The injection pattern is:

> Additional context retrieved for this query: {brand}: {fact}

This is a simulation of successful retrieval. It is not a measurement of real retrieval frequency.

## Sample size

Injected calls:

**4 brands × 20 prompts × 10 repeats = 800 calls**

Fact-usage judge calls:

**60 judged mentioned cells per brand × 4 brands = 240 calls**

The study reports approximately **1,050 new calls including judge scoring**.

## Primary outcome

### Mention rate

The primary outcome is whether the target brand appears in the generated answer.

For each brand:

**Lift = injected mention rate − published baseline mention rate**

## Brand-level results

| Brand | Baseline | Injected | Lift |
|---|---:|---:|---:|
| Brand A | 1.25% | 97.5% | +96.25pp |
| Brand B | 5.75% | 97.0% | +91.25pp |
| Brand C | 16.5% | 96.0% | +79.50pp |
| Brand D | 0.0% | 44.5% | +44.50pp |

Average mention-rate lift:

**77.9 percentage points**

## Fact-usage scoring

Mention alone does not establish that the injected fact influenced the answer content directly.

Therefore, a capped sample of mentioned cells was scored by a GPT-4o judge.

The judge checks whether the specific injected fact, or a clear paraphrase of it, appears in the response.

The study reports 60 judged cells per brand:

**240 judge calls total**

## Fact-usage results

| Brand | Judged cells | Fact usage |
|---|---:|---:|
| Brand A | 60 | 88.3% |
| Brand B | 60 | 46.7% |
| Brand C | 60 | 33.3% |
| Brand D | 60 | 33.3% |

Average fact-usage rate when mentioned:

**50.4%**

## Lift-to-fact-usage ratio

The diagnostic is:

**Lift-to-fact-usage ratio = mention-rate lift ÷ fact-usage rate**

Reported ratios:

| Brand | Ratio |
|---|---:|
| Brand A | 1.09 |
| Brand B | 1.96 |
| Brand C | 2.39 |
| Brand D | 1.34 |

Every brand had a ratio above 1.

The study uses this as evidence that mention-rate movement outpaced literal use of the injected fact.

## Interpretation

The mechanism is consistent with a **Linkage Gap**:

- the model can receive a relevant fact in context
- the brand's probability of appearing can rise substantially
- the model does not need to repeat the fact every time the brand appears

The result therefore should not be reduced to simple fact copying.

## Judge validation

The judge was manually spot-checked on **15 calls** against the raw response text.

- 14 of 15 matched
- 1 disagreement

The disagreement was described as a likely conservative false negative involving a close paraphrase.

## Limitations

1. The study does not measure actual retrieval frequency.
2. The “retrieved” state is simulated through system-message injection.
3. Only gpt-4o was tested.
4. Only four deliberately selected underperforming brands were tested.
5. The sample is not representative of all ecommerce brands.
6. Only consumer ecommerce was tested.
7. The injected condition uses 10 repeats per prompt versus 20 observations in the reused baseline.
8. Fact-usage scoring uses the same model family as generation, creating self-grading risk.
9. Only one injected fact was tested per brand.
10. Cross-platform and cross-model follow-up was outside this study.

## Data boundary

This package contains aggregate values explicitly reported in the study.

The complete row-level API log is not exposed in the supplied HTML, so no unavailable observations are reconstructed here.
