# Methodology — Reword the Question Three Ways. The Winner Mostly Stays the Same. (Study #40)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, Responses API with web_search_preview
- **Categories:** 8, identical to Source Stability
- **Design:** 3 phrasings per category, 5 repeats each, 2 independent rounds
- **Total calls:** 480 (240 search, 240 judge extraction)
- **Winner extraction:** gpt-4o LLM judge on free text, identical prompt to Source Stability
- **Statistics:** per-category split by same-phrasing vs. different-phrasing pairs, cluster-permutation test across categories as primary evidence

## Pre-registration and data

Pre-registered before the run. The design, the two hypotheses (formulation matters vs. stability holds across formulations), and the statistical plan were written into STUDY-DESIGN.md before either round was collected, so this page reports what the pre-registered test found, not a test picked after seeing the data.

## Results table

| Category | Winner stability (R1 → R2) | Cross-phrasing diff (R1 → R2) | Modal brand |
|---|---|---|---|
| Meal kit | 100.0% → 80.0% | +0.0pp → +20.0pplargest R2 diff | hellofresh |
| Electric toothbrush | 64.3% → 73.3% | +16.2pp → +2.7pplargest R1 diff | philips |
| Mechanical keyboard | 53.3% → 53.3% | +0.0pp → +9.3pp | razer / keychron |
| Headphones | 80.0% → 100.0% | +1.3pp → +0.0pp | sony |
| Robot vacuum | 100.0% → 100.0% | +0.0pp → +0.0pp | dreame |
| Air fryer | 100.0% → 100.0% | +0.0pp → +0.0pp | cosori |
| Gaming mouse | 100.0% → 100.0% | +0.0pp → +0.0pp | logitech |
| Bluetooth speaker | 100.0% → 100.0% | +0.0pp → +0.0pp | jbl |

## Findings and interpretation (from the study page)

### A specific objection, tested with data, not argued back on the thread

Source Stability's headline number, winner stability near 90%, came from repeating the exact same prompt ten times per category. That is a test-retest measure: how much noise is in the model's own repetition, holding the question completely fixed. When that number was cited on LinkedIn, Vural Cifci pointed to SparkToro's finding that two independent searches on the same topic return the same list less than 1% of the time, and argued stability is highest exactly where an incumbent is already entrenched, and reads closer to zero for a challenger. Both points are fair. Test-retest and cross-intent variance are genuinely different kinds of variance, and they can both be true at once, which is exactly why this study measures the second one directly instead of just asserting it in a reply.

Recycles the same eight categories and the same recency-cued anchor ("right now in 2026") as Source Stability, so the two studies' numbers sit side by side. The only thing that changes here is the question's syntax: "what's the best X", "which X should I buy", "can you recommend X", same category, same price or time anchor, same buying intent, three different ways of asking for it.


### Same buying intent, three ways of asking. Sometimes the winner moves, sometimes it doesn't.

Electric toothbrushes is the category where rewording made the most difference, in round 1. Here is exactly what each phrasing returned, five repeats each.


### Most categories showed almost no gap. A couple showed a real one.

For each category, every pair of calls within that category is split into two groups: pairs that used the same phrasing, and pairs that used two different phrasings. The number below is the difference in how often those two groups named the same winning brand, both rounds averaged.


### Round 1 vs. round 2, and the cluster test that decides it

Round 2 reran the entire design from scratch on an independent seed. Per the house standard for this series (independent unit = category, not individual call or pair), the primary test cluster-bootstraps and permutation-tests the eight per-category diffs, separately for each round.


### Does it matter more when nobody's clearly winning yet?

Vural's exchange raised a second, separate point: stability should be highest where an incumbent is already entrenched, and closer to meaningless for a challenger with no fixed position to defend. Splitting the eight categories by this study's own combined winner stability (both rounds pooled) into “incumbent” (a single brand named at least 90% of the time) and “open” (below that) gives a directional answer, not a confirmed one.


### Search fired almost every time, and the judge barely hedged

Every prompt carries the same recency cue that got 100% invocation in Source Stability and Live Retrieval, “right now in 2026” or “currently, in 2026”. Round 2 hit 120 of 120. Round 1 hit 117 of 120, three calls across meal kit, electric toothbrush, and gaming mouse answered without firing web search. High enough that search invocation itself is not a confound in the comparison above.

The winner is extracted by the identical gpt-4o judge prompt used in Source Stability, reading free text and naming whichever brand is presented first or called the top pick. All 3 low-confidence flags landed in round 1; round 2 had zero. Every winner-stability and cross-phrasing number on this page rests on a clear extraction in all but those 3 of 240 calls, which were excluded rather than guessed at.


### Wording alone is not a reliable lever on who wins

If cross-intent variance were the dominant force behind AI recommendations, a brand's odds should swing noticeably depending on how a buyer happens to phrase their question, a genuinely alarming idea for anyone trying to measure or influence recommendation share. This study instead found that in five of eight categories, wording made no detectable difference in either of two independent rounds, and in the cluster-level test that treats category as the unit of evidence, the overall effect of wording did not clear significance in either round on its own. That points toward what the earlier studies in this series have already found: what the model already associates with a brand (fame, ratings, authority claims, the fact it already occupies the answer) carries more weight than the specific syntax of the question asked. The one open thread worth someone testing further: whether that holds less firmly in categories with no clear incumbent yet.


### Three phrasings, not every possible phrasing

Three formulations per category is a specific, narrow slice of possible syntactic variation, not a claim that covers “any way of asking.” The judge logic and its known fragility (extracting a winner from free text, rather than a forced two-name choice) is recycled unchanged from Source Stability, on purpose, for comparability, which also means it inherits that study's limitations. Eight consumer product categories is a small sample by this series' own standard, and the incumbent-vs-open split above rests on just three open-category data points, too few to treat as confirmed rather than suggestive. Single model (gpt-4o) through the Responses API, not tested cross-model. The combined p=0.063 result sits close enough to conventional significance that a third independent round could plausibly tip it either way, this page reports two rounds, not three.


### Wording alone didn't reliably move the winner

Across most of the categories this study measured, the recommended brand held steady no matter how the buyer's question was phrased. Worth knowing where your own store actually stands with AI models before assuming a different search phrase would change the outcome.


Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Reword the Question Three Ways. The Winner Mostly Stays the Same.* Recommendation Intelligence Research™, Study #40. Zenodo. https://doi.org/10.5281/zenodo.22833586
