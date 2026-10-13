# Methodology — Rank First in the Cited Source, and the Model Always Agrees. Fourth Place Wins 1.2% of the Time. (Study #45)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Winner vs Loser
- **Conditions:** rank_1, rank_4, rank_15 (target's slot in the cited source)
- **Comparison:** forced two-way vs. named competitor, LLM judge
- **Calls:** 1,200 chat, 1,200 judge
- **Judge parse failures:** 0 of 1,200

## Pre-registration and data

Spot-checked before publication. Sample rows read from judged.json across all three conditions: the model's stated reasoning matches the mechanism directly, responses cite the source ranking itself ("because it is ranked higher in the roundup") as the entire justification for the pick. Cluster-mean and pooled rates were independently recomputed from the raw judged rows and matched the reported results to one decimal place in every condition.

## Results table

| Brand | Rank 1 | Rank 4 | Rank 15 |
|---|---|---|---|
| Barbaro Mojo | 100.0% | 5.0%only nonzero at rank 4 | 0.0% |
| BodyArtForms | 100.0% | 0.0% | 0.0% |
| Colored Organics | 100.0% | 0.0% | 0.0% |
| Hearthloom | 100.0% | 0.0% | 0.0% |

## Findings and interpretation (from the study page)

### A LinkedIn comment about a company that never got named

Olga Vainshtok posted an AEO audit for a B2B SaaS company: five AI engines could describe the company accurately when asked directly, but none of them recommended it in a "brand alternatives" roundup on a relevant, reasonably authoritative site, updated 3 months prior. Her company sat 4th of 17 in that roundup. In reply to our comment connecting her finding to our own Possession vs. Deployment gap, she added her own observation: being mentioned in a source isn't enough, position inside that source seems to matter too.

That's a testable claim we hadn't isolated before. Ghost Citation (unpublished) measures a different layer: within one response, how often a cited source promotes into a named product mention. Position Stability measures the brand's position in the model's own answer across repeats, not the brand's position inside the source the model is reading. Neither tests whether rank inside a cited source, on its own, changes the odds a brand becomes a candidate or a winner. So we built the test Olga's example describes almost exactly.


### One factor, three positions

Same 4 brands as Winner vs Loser, byte-identical: Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom, each against its existing competitor across 20 real buyer intents. The system message describes a synthetic "brand alternatives" roundup source with 17 slots, matching Olga's real example exactly. The competitor sits fixed at slot 2 in every condition. The other 15 slots are generic anonymized placeholders ("Other Brand 1" through "Other Brand 15"), no real names. The target brand's own slot is the one thing that changes: rank 1 of 17, rank 4 of 17 (Olga's exact real case), or rank 15 of 17 (near the bottom, not the literal last slot). Forced two-way comparison, same judge prompt as the rest of this series, unchanged.


### Selection is a switch. Candidacy is a dial

Two different things happen to two different measurements. Winning a forced comparison is almost perfectly binary, tied to sitting first in the source. Simply getting mentioned barely cares about position at all.


### The rank-1 effect holds on every brand. Rank 4 is close to zero on three of four

All 4 brands hit 100% selection at rank 1, no exceptions. At rank 4, three of four brands never won a single one of their 100 comparisons; only Barbaro Mojo won any (5 of 100). At rank 15, all 4 brands land at exactly 0%.


### Being cited isn't the win condition. Being cited first is

Olga's real example, 4th of 17 and zero engines naming the company, isn't an edge case. It's close to the expected outcome under this mechanism: a rank-4 brand still shows up in the model's awareness about 40% of the time, but almost never gets picked when a comparison is forced. If a roundup, directory, or "best of" list is the source a model is reading, sitting anywhere other than first in that list is worth close to nothing for actually being recommended, even though it still helps the model recognize the brand exists. That's a sharper, more specific version of what Source Stability found: the cited source can change and the winner mostly doesn't, and what Signal Hierarchy found: some signals dominate a comparison outright. Source rank looks like one of the strongest single-position effects measured anywhere in this series so far.


## Limitations

- Same small cohort as the rest of this series, not a new or broader sample.
- The roundup source is described in the system prompt text, not fetched via real browsing from a live URL. This tests sensitivity to a described position inside a claimed source, not a direct replica of how a model parses rank during real web retrieval.
- 1, 4, and 15 were chosen to match Olga's real example, not systematically swept across all 17 positions. A trend across 3 points is suggestive, not proof of the curve's exact shape between them.
- The competitor's own position never moved, which isolates the target's rank as the one variable but means we have no data on what happens when the competitor also sits at a worse position than the target.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Rank First in the Cited Source, and the Model Always Agrees. Fourth Place Wins 1.2% of the Time.* Recommendation Intelligence Research™, Study #45. https://atomfoundry.dev/research/source-rank-position. https://doi.org/10.5281/zenodo.23350942
