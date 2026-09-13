# Methodology

## Study metadata

- **Study:** Hidden Context
- **Study number:** #26
- **Published:** September 2026
- **Canonical URL:** https://atomfoundry.dev/research/hidden-context
- **Research series:** Recommendation Intelligence Research™
- **Model:** gpt-4o
- **Unit of analysis:** one model response to one real buyer-intent prompt under one hidden-context condition

## Research question

Does changing hidden upstream system-message context change whether a tested e-commerce brand is selected as the winner, while keeping the visible buyer prompt, brand, model, and detection method constant?

## Design

Five brands were deliberately selected because their published real-world recommendation baselines were weak enough to leave room for movement.

For each brand, the study reused one already-published real buyer-intent question. The visible prompt did not change across the new experimental conditions.

The manipulation was placed in the hidden system-message context. The shopper would not see the injected line and did not provide it.

### Conditions

| Condition | Description | New calls |
|---|---|---:|
| No context | Reused published control | 0 |
| User intent | Brand-blind instruction to provide a decisive, confident recommendation | 75 |
| Campaign origin | Fabricated claim that the user just saw an online advertisement for the tested brand | 75 |
| Brand exposure | Fabricated claim that the user has heard of the brand before | 75 |
| Feature exposure | Fabricated claim that the user saw a product page mentioning one real, verified brand fact | 75 |
| Brand + feature | Campaign-origin claim combined with the real feature fact | 75 |

The new experimental sample therefore contains 375 calls: 5 brands × 5 conditions × 15 repeats. The control contributes 100 previously published observations.

## Measurements

### Winner rate

Winner rate is the share of observations in which the tested brand is detected as the winning recommendation under the study's deterministic detection procedure.

Cohort-wide condition values are pooled with equal weight across the five brands.

### Candidacy rate

Candidacy asks whether the tested brand enters the recommendation/consideration set at all, rather than whether it wins.

The report states that under any of the four brand-specific conditions, candidacy reaches approximately 97–100% for nearly every brand.

### Condition delta

For each condition:

`condition delta = condition winner rate - no-context control winner rate`

Using the cohort-wide control of 22%:

- User intent: +12.7pp
- Brand exposure: +39.3pp
- Feature exposure: +42.0pp
- Brand + feature: +54.0pp
- Campaign origin: +66.0pp

## Brand detection

The study uses the same deterministic, case-insensitive substring brand-detection approach as the original report data. It does not use an LLM judge.

This removes model-based self-grading from the primary outcome measurement, but introduces a known blind spot: the detector relies on a closed, pre-registered list of known competitors.

A targeted review of all 244 records where a tracked brand was detected as the winner found one misclassification caused by an unlisted tool being named as the actual top pick. The corrected 34.7% user-intent result is used in the final report.

A manual spot-check of 20 complete responses across conditions found no additional errors.

## Statistical testing

The report uses a **10,000-reshuffle label-shuffle permutation test** for condition-vs-control comparisons.

All four brand-specific hidden-context conditions were reported as highly significant relative to the no-context control, with p < 0.0001.

The dataset metadata also specifies cluster bootstrap confidence intervals. The clustering structure follows the repeated observations within brand/condition rather than treating every response as independent evidence about the universe of brands.

## Exploratory baseline interaction

A pre-registered exploratory check with n=5 correlated each brand's real-world baseline recommendation rate with the amount of lift under hidden context.

Reported correlations:

- Candidacy lift: r = -0.63
- Winner lift: r = -0.73

These are explicitly exploratory and should not be treated as confirmed population-level effects.

## Interpretation

The experiment is designed to separate **candidacy** from **selection**.

The key result is not simply that context changes the output. Every brand-specific condition did that. The more interesting result is the ordering:

`No context < User intent < Brand exposure < Feature exposure < Brand + feature < Campaign origin`

with campaign origin reaching 88% winner rate.

The study therefore provides controlled evidence that hidden framing about prior brand exposure can have a larger effect on selection than a concrete, truthful product fact in this specific setup.

## Limitations

- Five brands only.
- Brands were deliberately chosen for weak real-world baselines and are not a representative cross-brand sample.
- One consumer-ecommerce category mix.
- One model family/model: gpt-4o.
- One buyer-intent prompt per brand.
- Fabricated exposure claims were experimental context and did not describe real events.
- The no-context control was reused from previously published data rather than rerun.
- The H4 baseline-interaction correlations are exploratory at n=5.
- The condition ordering should not be generalized as a universal hierarchy of context effects.
- Deterministic substring detection can miss or misclassify outputs outside the closed competitor list.
- The experiment measures simulated system-message manipulation, not naturally occurring real-world personalization or advertising exposure.

## Data boundary

This package contains the aggregate values explicitly reported on the canonical study page. It does not claim to reproduce any unpublished row-level response dataset that is not exposed by the source.

## Source

Canonical study page: https://atomfoundry.dev/research/hidden-context
