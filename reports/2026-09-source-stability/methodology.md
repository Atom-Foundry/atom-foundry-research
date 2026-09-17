# Methodology -- The Cited Source Changes. The Winner Almost Never Does.

Reproduced from the published study page. All figures are aggregate
results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, Responses API with web_search_preview
- **Categories:** 8 real consumer product categories
- **Design:** 10 repeats per category, 2 independent rounds
- **Total calls:** 320 (160 search, 160 judge extraction)
- **Winner extraction:** gpt-4o LLM judge on free text, no forced two-name choice
- **Statistics:** per-category split by citation-domain overlap (Jaccard >= 0.5 vs < 0.5); cluster-permutation test across categories as primary evidence
- **Prompts:** recency-cued by design ("right now in 2026"); a small pilot confirmed 100% invocation across 4 candidate categories before the full 8-category design was committed to, and the 100% rate held across the full real run

This study breaks from the rest of the series on purpose: Winner vs Loser,
Authority, and Brand Familiarity all use 4 synthetic brands with a forced
two-name choice, because nothing there is actually being searched for.
Live search needs real content to find, so this study uses real product
categories with real, already-competing brands, and an open-ended "what's
the best X" question instead.

## Worked example: budget gaming mice, round 1, all 10 repeats

Prompt: "What's the best budget gaming mouse right now in 2026?"

- 9 of 10 runs: identical domain set (pickedtested.com, ryugear.in,
  search.rakuten.co.jp, coolbox.pe, ebay.co.uk, itechguides.com,
  overclockers.co.uk, rtings.com) -> Logitech
- 1 of 10 runs: one domain swapped (ttkgear.com replaced ryugear.in) -> Logitech (unchanged)

Every one of the 45 possible pairs across those 10 runs shared at least 7
of 8 domains, so this category-round could not enter the primary
statistical test (no "different source" comparison group existed). It is
the most extreme version of the study's own finding: both source and
winner stayed almost completely fixed.

## Winner stability and source stability by category (both rounds)

| Category | Winner stability (R1 -> R2) | Source stability (R1 -> R2) | Cluster diff (R1 / R2) |
|---|---|---|---|
| Meal kit | 40.0% -> 60.0% | 2.2% -> 2.2% | +39.3pp / +30.0pp |
| Electric toothbrush | 80.0% -> 100.0% | 13.3% -> 48.9% | +25.8pp / +0.0pp |
| Mechanical keyboard | 100.0% -> 100.0% | 48.9% -> 20.0% | +0.0pp / +0.0pp |
| Air fryer | 100.0% -> 100.0% | 6.7% -> 13.3% | +0.0pp / +0.0pp |
| Bluetooth speaker | 100.0% -> 100.0% | 26.7% -> 46.7% | +0.0pp / +0.0pp |
| Headphones | 100.0% -> n/a (R2 not computable) | 33.3% -> n/a | +0.0pp / n/a |
| Robot vacuum | n/a (R1 not computable) -> 100.0% | n/a -> 46.7% | n/a / +0.0pp |
| Gaming mouse | 100.0% -> 100.0% | 80.0% -> 24.4% | n/a / n/a (no low-overlap group, both rounds) |

4 of 16 category-rounds could not enter the pairwise comparison at all --
not from missing/low-confidence data, but because every repeat-pair in
that category-round shared >= 50% of its cited domains, leaving no
"different source" group to compare against.

## Primary statistical test

Cluster-permutation test across categories, independent unit = category,
not individual call.

- Round 1: n=6 usable categories, mean diff +10.8pp, 95% CI [0.0, +24.0]pp, p=0.501
- Round 2: n=6 usable categories, mean diff +5.0pp, 95% CI [0.0, +15.0]pp, p=1.000
- Combined (12 category-clusters across both rounds): mean diff +7.9pp, 95% CI [0.0, +16.5]pp, p=0.248

None of the three clears significance at any conventional threshold. This
supports the winner being largely independent of which exact source search
happened to surface, with meal kits as the one category pulling the
average up in both rounds and still not enough on its own to move the
combined result past chance.

## Robustness

- 0 of 160 judge calls (both rounds) flagged low-confidence.
- The analysis script's defensive design returns no result rather than
  fabricate a diff when one comparison side is empty (built in from the
  start). Triggered for headphones (round 2), robot vacuums (round 1), and
  gaming mice (both rounds independently).

## Limitations (stated on the published page)

- Winner extraction here uses an LLM judge reading free text, not a forced
  two-name choice like the rest of this series -- a more fragile design,
  even though this run had zero low-confidence flags.
- "Source" is defined as the full set of cited domains per response,
  compared by Jaccard similarity between repeat pairs -- one reasonable
  definition, not the only one a different study could choose.
- 4 of 16 category-rounds could not enter the primary test, so the combined
  result effectively rests on 12 category-rounds, smaller than most of this
  series' cluster counts.
- Eight consumer product categories is a small, narrow sample; does not
  generalize to services, B2B, or categories with a single dominant market
  leader.
- Single model (gpt-4o) through the Responses API, not tested cross-model.
  Meal kits' outlier status is one data point from one study, not
  independently replicated elsewhere.
