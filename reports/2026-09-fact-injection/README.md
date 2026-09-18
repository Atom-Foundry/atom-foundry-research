# Give the Model the One Fact It's Missing. The Brand Goes From Invisible to Everywhere.

Atom Foundry — Recommendation Intelligence Research™ · Study #25
Published: 2026-09-08
DOI: [10.5281/zenodo.22757248](https://doi.org/10.5281/zenodo.22757248)

> Put one real, verified fact directly in front of the model, as if retrieval had just succeeded. The brand can move from barely mentioned to near-universal.

## Research question

Does directly injecting one real, verified fact about an underperforming brand change whether the brand gets mentioned in AI-generated shopping answers?

This is the causal follow-up to **Possession vs Deployment**.

That earlier study measured a passive gap: a model can possess facts about a brand without deploying them in the answer. This study changes the mechanism directly by placing one verified fact into the model's context at answer time.

## Headline results

| Metric | Result |
|---|---:|
| Brands tested | 4 |
| Buyer prompts per brand | 20 |
| Repeats per prompt | 10 |
| Injected calls | 800 |
| Judge calls | 240 |
| New calls | ~1,050 |
| Average mention-rate lift | 77.9pp |
| Average fact-usage rate, when mentioned | 50.4% |
| Brands with lift-to-fact-usage ratio > 1 | 4 of 4 |

The four brands were deliberately selected because their published baseline recommendation rates were low, from **0% to 16.5%**.

## The result

Three brands moved from barely mentioned to near-universal:

| Brand | Published baseline | With fact injected | Lift |
|---|---:|---:|---:|
| Brand A | 1.25% | 97.5% | +96.25pp |
| Brand B | 5.75% | 97.0% | +91.25pp |
| Brand C | 16.5% | 96.0% | +79.50pp |
| Brand D | 0.0% | 44.5% | +44.50pp |

The average lift across the four brands was **77.9 percentage points**.

Brand D had the smallest lift. The study notes that its injected fact was less directly relevant to the buyer questions than the facts used for the other brands.

## What was changed

For each brand, Atom Foundry identified one real, verified and distinctive fact.

That fact was injected into the system message using the pattern:

> Additional context retrieved for this query: {brand}: {fact}

The wording is deliberately framed as retrieved context. It simulates the point at which a retrieval step has already succeeded.

The model then received the brand's own already-published real buyer questions, unmodified.

The response was first checked for whether the brand appeared at all.

On a capped sample of mentioned cells, a GPT-4o judge then checked whether the specific injected fact was actually cited or clearly paraphrased.

## Experimental structure

The new injected experiment contains:

**4 brands × 20 buyer prompts × 10 repeats = 800 injected calls**

Fact-usage scoring added:

**60 judged mentioned cells per brand × 4 brands = 240 judge calls**

The baseline is reused from the already-published Recommendation Reports. It is not regenerated for this study.

The page reports approximately **1,050 new calls including judge scoring**.

## Mention rate vs. fact usage

A key diagnostic is that the model did not simply repeat the injected fact every time it mentioned the brand.

| Brand | Fact usage when mentioned | Lift-to-fact-usage ratio |
|---|---:|---:|
| Brand A | 88.3% | 1.09 |
| Brand B | 46.7% | 1.96 |
| Brand C | 33.3% | 2.39 |
| Brand D | 33.3% | 1.34 |

Every brand had a ratio above 1.

That means the mention-rate lift was larger than the rate at which the specific injected fact was actually cited or paraphrased.

Brand A came closest to a 1:1 coupling.

Brand C showed the widest gap: the brand was mentioned readily, while the specific injected fact appeared in only one third of judged mentions.

## Interpretation

The result supports a narrow mechanism:

**Putting a relevant, verified fact into the model's context can dramatically increase the probability that an underperforming brand is mentioned.**

But the mechanism is not simply:

**fact appears → model repeats fact → brand gets recommended.**

The response data show something more interesting.

The injected fact can change the model's treatment of the brand even when the final answer does not explicitly repeat that fact.

The study interprets this as evidence consistent with a **Linkage Gap**: information may be available to the model but fail to reach the generated answer. Directly placing the fact in context can close that linkage problem.

## What this does not prove

- It does not measure how often a real retrieval system would surface the same fact for the same query.
- “Retrieved” is simulated, not measured.
- Only **gpt-4o** was tested.
- Only four deliberately selected underperforming brands were tested.
- Only one category mix, consumer ecommerce, was used.
- The injected condition used 10 repeats per prompt, while the reused baseline has 20 observations per prompt.
- Fact usage was judged by the same model family that generated the responses, creating a self-grading risk.
- Only one injected fact was tested per brand.
- The cross-platform and cross-model follow-up was not part of this study.

## Judge validation

The fact-usage judge was manually checked on **15 calls** against the raw response text.

**14 of 15 matched.**

The one disagreement was a likely conservative false negative: a response closely paraphrased the injected fact but was marked as not using it.

If anything, that means the reported fact-usage rates may be slightly understated rather than inflated.

## Reproducibility

The source study exposes:

- the experimental question
- model and injection mechanism
- sample structure
- baseline and injected mention rates
- fact-usage rates
- lift-to-fact-usage ratios
- judge validation
- limitations

The complete row-level API log is not exposed in the supplied HTML. This repository records the reported aggregate results and methodology without inventing unavailable raw observations.

## Source

https://atomfoundry.dev/research/fact-injection

## Citation

Atom Foundry (2026). *Give the Model the One Fact It's Missing. The Brand Goes From Invisible to Everywhere.* Recommendation Intelligence Research™, Study #25. Zenodo. https://doi.org/10.5281/zenodo.22757248
