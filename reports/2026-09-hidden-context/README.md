# Tell the Model You Saw an Ad. It Recommends That Brand 88% of the Time

**Study #26 · Recommendation Intelligence Research™ · September 2026**

> Same prompt, same brand, same model. Only one hidden line in the system message changes. A fabricated claim that the shopper just saw an ad for the brand produced an 88% winner rate, the largest lift of any condition tested.

## Research question

Does hidden upstream context, invisible to the shopper and absent from the user's prompt, change which e-commerce brand an AI system recommends?

This study turns the observational **Candidacy vs Selection** distinction into a controlled manipulation. Five deliberately weak-baseline brands were tested with the same real buyer-intent prompt, the same model, and the same deterministic brand-detection method. Only a single hidden system-message condition changed.

## Headline results

| Metric | Result |
|---|---:|
| Brands tested | 5 |
| New model calls | 375 |
| Reused no-context control observations | 100 |
| Total observations represented | 475 |
| No-context winner rate | 22.0% |
| User-intent, brand-blind | 34.7% |
| Passive brand exposure | 61.3% |
| Real feature exposure | 64.0% |
| Brand + feature | 76.0% |
| Campaign-origin / fabricated ad exposure | **88.0%** |
| Brand-specific conditions significant vs control | 4/4, p < 0.0001 |

## Experimental conditions

1. **No context (control)** — reused from already-published data; no new calls.
2. **User intent** — brand-blind instruction that the shopper wants a decisive, confident recommendation.
3. **Campaign origin** — fabricated claim that the user just saw an online advertisement for the tested brand.
4. **Brand exposure** — fabricated claim that the user has heard of the tested brand before, without further detail.
5. **Feature exposure** — fabricated claim that the user saw a product page mentioning one real, verified fact about the brand.
6. **Brand + feature** — campaign-origin claim combined with the real product fact.

The four brand-specific conditions were each run 15 times per brand, giving 375 new calls across five brands and five new conditions. The no-context cohort was reused rather than rerun.

## Main finding

Every brand-specific hidden-context condition increased winner rate relative to the 22% no-context control. But the effects were not ordered by how concrete or truthful the injected information was.

The fabricated **campaign-origin** condition produced an 88% winner rate. That beat the combined **brand + feature** condition at 76%, the real feature condition at 64%, and passive brand exposure at 61.3%.

The result is notable because the strongest manipulation was not the most information-rich one. A bare claim that the shopper had just seen an advertisement produced the largest measured lift.

All four brand-specific conditions were significant against the no-context control under a 10,000-reshuffle label-shuffle permutation test, with p < 0.0001 for the four brand-specific comparisons.

## Candidacy vs Selection

The study separates two outcomes:

- **Candidacy:** does the tested brand enter the recommendation/consideration set?
- **Winner rate:** does the tested brand actually win against the other brands detected in the response?

Under the brand-specific hidden-context conditions, candidacy jumped to roughly **97–100% for nearly every brand**, even for brands with weak real-world baselines.

Winner rate remained much more heterogeneous.

This supports the central distinction:

> **Candidacy is a switch. Selection is a contest.**

Getting a brand into context is not the same thing as making it win once it is there.

## Per-brand pattern

The campaign-origin condition moved the five anonymized brands as follows:

| Brand | Published no-context baseline | Campaign-origin condition | Lift |
|---|---:|---:|---:|
| Brand A | 10.0% | 100.0% | +90.0pp |
| Brand B | 0.0% | 86.7% | +86.7pp |
| Brand C | 0.0% | 100.0% | +100.0pp |
| Brand D | 0.0% | 53.3% | +53.3pp |
| Brand E | 100.0% | 100.0% | 0.0pp |

Brand identities are anonymized because the exposure claims in the experiment were fabricated and did not describe real events.

The pattern also illustrates floor and ceiling effects. The brand already winning 100% of the time had no measurable room to move.

## Exploratory baseline interaction

An exploratory, pre-registered check across the five brands found negative correlations between real-world baseline recommendation rate and hidden-context lift:

- Candidacy lift: **r = -0.63**
- Winner lift: **r = -0.73**

These are reported as exploratory because **n = 5** is too small for them to be treated as confirmed general effects.

## Data integrity and correction

Brand detection used a deterministic, case-insensitive substring method and no LLM judge. This avoids self-grading bias but has a closed competitor-list blind spot.

A targeted review of all **244 records** where a tracked brand was detected as the winner found exactly one real misclassification. In a brand-blind condition, the model explicitly named an unlisted tool as its top pick, but because that tool was outside the pre-registered competitor list, the detector still marked the tracked brand as the winner.

Correcting that record changed the relevant cohort-wide winner rate from 36.0% to **34.7%**. The correction did not change any statistical conclusion.

A manual spot-check of 20 full responses across conditions found no additional errors.

## What this result means

The experiment shows that changing hidden upstream context can materially change recommendation outcomes even when the shopper's visible prompt, the brand, and the model remain constant.

More specifically, in this test:

- prior-exposure framing mattered strongly;
- a fabricated ad-exposure claim outperformed a real product fact;
- adding more concrete information did not produce the largest effect;
- candidacy and selection behaved differently.

The result is a reason to treat context as part of the recommendation mechanism, not merely as a wrapper around the visible prompt.

## What this does not prove

This study does **not** show that advertising universally causes AI systems to recommend a brand.

It does not show that the model actually knew the user had seen an ad. The exposure claims were deliberately fabricated system-message context.

It does not establish that the same effect size will occur across other models, categories, prompts, brands, or real user conversations.

It also does not prove that campaign-origin framing is inherently stronger than truthful product information in every setting. The ordering is observed in this controlled cohort.

## Reproducibility

The study uses:

- **Model:** gpt-4o throughout
- **Brands:** 5 deliberately weak-baseline e-commerce brands
- **New calls:** 5 brands × 5 new conditions × 15 repeats = 375
- **Control:** 100 reused observations from published no-context data
- **Detection:** deterministic, case-insensitive substring matching
- **Statistics:** cluster bootstrap confidence intervals and a 10,000-reshuffle label-shuffle permutation test
- **Prompt:** one already-published real buyer-intent question per brand

See [`methodology.md`](methodology.md) for the detailed design and limitations.

## Files

- [`README.md`](README.md) — study overview and results
- [`methodology.md`](methodology.md) — experimental design, measurement and limitations
- [`experiment-summary.csv`](experiment-summary.csv) — aggregate experiment data
- [`Charts/`](Charts/) — reproducible SVG charts and chart documentation

## Source

Canonical study page: https://atomfoundry.dev/research/hidden-context
