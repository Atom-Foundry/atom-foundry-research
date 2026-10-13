# Methodology — Rating Recommendations Don't Move When You Reword the Question. Price Recommendations Do. (Study #41)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 0.7
- **Design:** 16 contested intents × 5 phrasings × 10 runs, per signal
- **Total calls:** 1,600 (800 price, 800 specs)
- **Pick extraction:** majority vote of 10 runs per phrasing, identical rule to published Method 6
- **Statistics:** cluster-permutation test, unit=intent (n=16 per signal), 10,000 permutations
- **Correction:** Bonferroni ×3 (price vs. rating, specs vs. rating, price vs. specs)

## Pre-registration and data

Same source file, same scenarios, only the signal filter changes. Both new CSVs are generated from the exact same phase3_raw.csv Recommendation Confidence already used, filtered to signal=price or signal=specs, a_had_better_fact=True, run=1 instead of signal=rating. The rating-signal comparison number below (0 of 16) is the already-published result, reused unchanged, not rerun for this page.

## Results table

| Comparison | Flip-rate diff | Raw p | Bonferroni-corrected p (×3) | Result |
|---|---|---|---|---|
| Price vs. rating | +43.8pplargest gap | p=0.0075 | p=0.0225 | Significant |
| Specs vs. rating | +12.5pp | p=0.4936 | p=1.0 | Not significant |
| Price vs. specs | +31.2pp | p=0.1137 | p=0.341 | Not significant |

## Findings and interpretation (from the study page)

### A disclosed gap, closed with the exact same design, not a new one

Recommendation Confidence's own limitations section said it plainly: “Methods 5 through 7 do not repeat this design for the price or specs signal types, so the cross-model and phrasing-robustness findings are demonstrated for the rating signal specifically, not confirmed identically for every signal type in this series.” That's a testable claim, not just a caveat, and Method 6 (phrasing perturbation) was the cheapest of the three to extend. So this reuses the identical 16 contested intents from Candidate Evaluation's phase 3 run, the identical 5 phrasing templates, and the identical 10-runs-per-phrasing design, the only change is loading the price-signal and specs-signal fixed fact pairs instead of the rating-signal ones. Nothing new was generated, no scenario was reshuffled.


### Same facts, five phrasings. Four of five land on a different brand than the first.

Best cat litter for odor control, Arm & Hammer versus Dr. Elsey's, Dr. Elsey's holding the better fixed price fact. Here is exactly what each phrasing's 10 runs returned.


### Rating holds. Specs mostly holds. Price doesn't.

Same question as the published Method 6, asked of two more signal types: across the 16 contested intents and 5 phrasings, how often does the majority-vote pick change depending on which phrasing was used.


### The cluster-permutation test that decides it

Per the house standard for this series, the primary test treats each intent as the independent unit (16 per signal, not 800 individual calls), permutation-tests the flip-rate difference between signal pairs, and Bonferroni-corrects across the 3 comparisons this page makes.


### The signal that flips the most hedges the least

The same Hyland-style hedge/booster lexicon from the rest of this series, applied to each call's one-sentence reason. If hedge language tracked real instability, price, the least stable signal, should hedge the most. It's the opposite.


### The stable-decision finding was never a universal one

Recommendation Confidence's headline, that the model's pick barely moves no matter how the question is phrased, held completely for the rating signal: 0 of 16 flips, 5 phrasings, 10 runs each. It was always fair to ask whether that held for other kinds of injected facts, and it doesn't uniformly. A brand whose advantage is a lower price should not assume a reworded question leaves its recommendation odds where they were, 7 of 16 price-based comparisons in this sample landed on a different brand depending on phrasing alone. A brand whose advantage is a spec claim sits closer to rating's stability, but not confirmed identical to it either, 2 of 16 flipped, a real number even if this sample can't rule out chance. The practical read: don't generalize a phrasing-robustness result from one signal type to another without testing it, this series' own headline finding is the proof that assumption can be wrong.


### A closed gap, and two new open ones

The specs result (2 of 16, p=1.0 corrected) is not confirmation that specs behaves like rating, it's an absence of a detected difference at this sample size, a different claim. Twice rating's raw flip rate is not a small number to wave away; a larger sample could plausibly find specs closer to price than to rating. The majority-pick rule inherited unchanged from the published Method 6 breaks 10-run ties arbitrarily by insertion order, and 2 of the 7 price flips and 1 of the 2 specs flips pass through at least one dead-even 5-5 phrasing, meaning some of what's counted as “flipped” may be closer to genuine model indecision than a clean phrasing-driven swing. Cross-model (method 7) and the logprobs/self-report confidence methods (3 and 4) remain rating-only, this page closes the phrasing-perturbation leg of the disclosed gap specifically, not the whole gap. Single model (gpt-4o), single temperature (0.7), same 16 intents and 5 phrasing templates as the rest of this sub-series, not independently re-designed for price and specs.

Everything here is correlational and observational within a controlled prompt design, not a causal test on a real store, the same standing limitation as every study in this series. It measures whether a model's stated pick moves when the question's wording changes, holding the underlying facts fixed; it does not measure what happens if a real brand's own price or spec claims change in the wild.


Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Rating Recommendations Don't Move When You Reword the Question. Price Recommendations Do.* Recommendation Intelligence Research™, Study #41. https://atomfoundry.dev/research/phrasing-stability-by-signal. https://doi.org/10.5281/zenodo.23350256
