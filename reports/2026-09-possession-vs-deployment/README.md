# The Model Knows 6 Facts About Your Brand. It Uses One

**Atom Foundry — Recommendation Intelligence Research™ · Study #23**

> We asked gpt-4o what it knows about 9 brands, then checked those claimed facts against 4,000 already-collected real buyer-question responses. Across 1,392 fact-cell checks, 75.8% of possessed facts never appeared when the model actually made a recommendation.

## Research question

When a model can state specific facts about a brand from memory, does it actually deploy those facts when making a recommendation?

This study separates two things that are easy to conflate:

- **Possession:** the model can state a fact when directly asked.
- **Deployment:** that fact appears, even paraphrased, in a real buyer-question response where the brand is mentioned.

The source describes these as two separate call types measured against each other. fileciteturn60file0L541-L551

## Headline results

| Result | Finding |
|---|---:|
| Brands tested | **9** |
| Possession probe | **27 calls** |
| Existing deployment observations reused | **3,600** |
| Cells scored | **308** |
| Fact-cell pairs checked | **1,392** |
| Possessed facts never deployed | **75.8%** |
| Actually deployed | **24.2%** |
| 95% CI for gap | **69.9–81.6%** |
| Deployment vs recommend-rate correlation | **r = -0.04, p = 0.91, n = 9** |

The study's metadata reports the 75.8% gap and 24.2% deployment rate directly. fileciteturn60file0L65-L85

## The design

### Phase 1 — Possession

In fresh conversations with no purchase context, gpt-4o was asked what it knows about each brand, including distinctive and checkable facts about products, pricing, differentiation and competitors.

The probe was run **3 times per brand**.

Only facts that appeared in substance across at least **2 of the 3 runs** were retained as stable possessed facts. This was intended to prevent one-off phrasing from becoming a measured fact. fileciteturn60file0L541-L543

### Phase 2 — Deployment

Instead of collecting another 3,600 expensive buyer-question responses, the study reused the deployment dataset from the published Recommendation Reports.

The source contains **400 buyer-question observations per brand**, with full response text and a brand-mentioned flag.

Every sampled cell where the brand was mentioned was then checked against that brand's possessed-fact list: does this specific fact appear in the recommendation response, including a paraphrase?

A tenth brand, Topicals, was excluded because it was mentioned in **0 of 400** observations. That is treated as a Candidacy failure, not as a deployment/linkage-gap observation. fileciteturn60file0L542-L553

## Finding 1: most possessed facts never reach the recommendation

Across **1,392 fact-cell checks**:

**75.8% never appeared.**

The inverse is a **24.2% deployment rate**.

In other words, when the model is asked directly, it can produce specific brand facts confidently. But when it reaches an actual recommendation moment, most of those facts do not appear in the generated response. fileciteturn60file0L558-L563

This is the central distinction of the study:

**Knowing a fact is not the same as deploying a fact.**

## Finding 2: deployment varies substantially by brand

| Brand | Deployment rate |
|---|---:|
| Onyx Coffee Lab | 8.8% |
| Peak Design | 17% |
| Branch | 20.7% |
| Bellroy | 22.5% |
| Rumpl | 23% |
| Wild One | 27% |
| Boll & Branch | 35.6% |
| Caraway | 37.5% |
| Zigpoll | 40% |

The source explicitly flags Zigpoll as the least reliable single estimate because only **5 cells** were available. Branch is also thinner at 23 cells. The seven brands with the full 40-cell sample range from 8.8% to 37.5%. fileciteturn60file0L563-L617

The range matters. The headline is not saying every brand deploys facts at exactly 24.2%. It is saying that the aggregate gap is large, while the brand-level rate varies considerably.

## Finding 3: winning more does not mean deploying more

A natural hypothesis would be that brands recommended more often are also the brands whose facts are deployed more often.

The source tested that directly.

Deployment rate vs published recommend rate:

**r = -0.04, p = 0.91, n = 9**

The source calls this an underpowered negative result, not a confirmed universal null. But there is no visible relationship in this cohort. fileciteturn60file0L622-L628

That is strategically useful because it suggests two mechanisms should not automatically be treated as the same lever:

**winning more ≠ deploying more of your known facts.**

## Finding 4: possession was not the bottleneck

The broader research series already showed that when a comparison fact is placed directly in front of the model at the decision point, a better rating can flip the outcome **100% of the time** in the tested head-to-head setup.

This study shows the complementary problem:

The model can already know the fact, but that fact may fail to make the transition from memory into the recommendation sentence.

The source therefore frames the bottleneck as the path from:

**memory → deployment at the decision point**

rather than simply:

**does the model know the brand?** fileciteturn60file0L632-L638

## A useful exclusion: Topicals

Topicals appears in the underlying Recommendation Reports cohort but was excluded from this study because it was mentioned in **0 of 400** buyer-question observations.

There is no deployment event to score.

The source deliberately keeps this separate from the linkage-gap mechanism:

**Candidacy failure is different from Linkage Gap.** fileciteturn60file0L652-L680

## Methodology and scoring

The study used:

- **gpt-4o throughout**
- 9 brands
- 3 possession runs per brand
- 3,600 reused deployment observations
- approximately 280 new scoring calls
- 308 sampled cells
- 1,392 fact-cell pairs
- model-judged fact matching
- cluster bootstrap confidence intervals
- label-shuffle permutation testing

The possession facts were merged only when they appeared in substance across at least two of three possession runs. fileciteturn60file0L541-L551

## What this does not prove

- It does not show that 75.8% of all facts a model knows about every brand are universally ignored.
- The possession list depends on the extraction prompt and the definition of a stable fact.
- The actual merged stable fact count varied by brand rather than being a literal fixed six facts.
- Deployment data were collected one to three weeks before the possession probe rather than being time-paired.
- The deployment side uses previously collected recommendation responses rather than a newly randomized deployment experiment.
- The same model family is involved in possession, deployment generation and scoring, creating a self-grading limitation.
- The cohort contains nine brands and consumer ecommerce only.
- Cross-model and cross-platform testing is a separate follow-up.

## The main takeaway

The interesting question is no longer simply:

**Does AI know my brand?**

It can.

The harder question is:

**When AI knows something useful about my brand, does that fact actually reach the moment of recommendation?**

In this study, most did not.

## Files

- `README.md` — study overview, findings, interpretation, and limitations
- `methodology.md` — experimental design, scoring, statistics, and boundaries
- `experiment-summary.csv` — aggregate metrics using the standard Atom Foundry schema
- `Charts/README.md` — chart descriptions and provenance
- `Charts/possession-vs-deployment-overview.svg`
- `Charts/deployment-rate-by-brand.svg`
- `Charts/deployment-vs-recommendation-correlation.svg`

## Source

Published study: https://atomfoundry.dev/research/possession-vs-deployment
