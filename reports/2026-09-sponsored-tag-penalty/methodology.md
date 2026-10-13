# Methodology — Mark the Listing Sponsored, and It Loses 18.4 Points in a Head-to-Head Pick (Study #43)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Winner vs Loser
- **Conditions:** organic vs. sponsored label, target only
- **Comparison:** forced two-way vs. named competitor, LLM judge
- **Total calls:** 800 chat, 800 judge (all rows judged)
- **Judge prompt:** unchanged from Winner vs Loser

## Pre-registration and data

Pre-registered before the run. The design, the single factor, and the two competing outside hypotheses it was meant to adjudicate were written into STUDY-DESIGN.md before the run, so this page reports what the pre-registered test found.

## Results table

| Brand | Organic | Sponsored | Penalty |
|---|---|---|---|
| BodyArtForms | 100.0% | 97.0% | 3.0ppnear ceiling |
| Barbaro Mojo | 71.0% | 62.0% | 9.0pp |
| Hearthloom | 88.0% | 60.0% | 28.0pp |
| Colored Organics | 38.0% | 4.0% | 34.0ppnear floor |

## Findings and interpretation (from the study page)

### Two outside numbers disagreed. We had the methodology to settle it ourselves

Zhao Hanbo (Nile) published real data across 3,602 ChatGPT ad placements and 91 paired brand-same-question comparisons, ad on versus off. Buying the placement moved the rate at which the model named the brand in text by -0.3pp, essentially nothing. His conclusion: the ad slot you buy and the recommendation slot you earn are two separate systems.

Allouah, Besbes, Figueroa, Kanoria and Kumar (ACM Web Conference 2026) found the opposite pattern testing across multiple agents and providers: a consistent penalty for a sponsored tag and a reward for platform endorsement, with the strength varying by provider. Juozas Kaziukenas (Marketplace Pulse) demonstrated the same thing concretely, asking Meta Muse to pick from Walmart's "aaa batteries" results (8 sponsored listings across two rows) and watching it never once shortlist a sponsored one, despite clearly seeing them in the browser.

Rather than side with one outside number over the other, we ran the same question through our own methodology, the same forced two-way comparison and judge prompt already validated in Winner vs Loser.


### One label, nothing else changes

4 brands were reused byte-identical from Winner vs Loser: Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom, each against its existing competitor across 20 real buyer intents. Only one thing varies between conditions: whether the target brand's listing is described as "a standard search result" or as "marked as a Sponsored result." The competitor is described as a standard result in both conditions, so the sponsored label is the only variable in play, isolated from rating, specificity, and format, which stayed untouched from the original brand data.


### The penalty is real, and it is not small

Across all 4 brands (cluster mean), the organic label won 74.2% of forced comparisons. The sponsored label won 55.8%, an 18.4 point drop (3 to 34 points per brand). Same brand, same claim, same competitor, the only difference was one sentence describing the listing as sponsored instead of standard. This sits closer to Allouah et al.'s active-penalty finding than to Zhao Hanbo's near-zero one, though the two are not measuring quite the same thing, real ChatGPT ad placements versus a simulated text label, see limitations below.


### Same direction on every brand. Size varies a lot

The penalty never flips direction, all 4 brands lose ground when sponsored. But the size ranges from 3 points to 34 points, and the two ends of that range line up with ceiling and floor effects rather than a clean, uniform penalty.


### Not zero. A real, direction-consistent penalty

Zhao Hanbo's near-zero finding and this result are not necessarily in conflict, real ChatGPT ad placements may render and get treated differently than the text label we tested, and his sample measured mention rate in an open response rather than a forced comparison against a named competitor. What this study adds is a controlled, isolated answer to a narrower question: when a model is explicitly told a listing is sponsored and asked to pick between it and a named alternative, it picks the sponsored one less often, on every brand tested, by a margin too large to call noise.


### Is a sponsored tag costing you the final pick ?

See how your store is positioned in AI comparisons before you spend on placement.


## Limitations

- Same small cohort as Winner vs Loser and Negative Reputation, not a new or broader sample. A wider cohort is an open follow-up.
- Simulated via system-prompt text, not a real ChatGPT ad placement, Meta Muse browsing session, or marketplace API. Tests sensitivity to a stated signal, not a direct replica of any platform's ad pipeline.
- gpt-4o only, single round. Allouah et al. found penalty strength varies across providers, replication on other models is an open follow-up.
- Whether query-conditional description changes can recover the penalty (the paper's proposed defense) is a separate, not-yet-designed follow-up study.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Mark the Listing Sponsored, and It Loses 18.4 Points in a Head-to-Head Pick* Recommendation Intelligence Research™, Study #43. https://atomfoundry.dev/research/sponsored-tag-penalty. https://doi.org/10.5281/zenodo.23350804
