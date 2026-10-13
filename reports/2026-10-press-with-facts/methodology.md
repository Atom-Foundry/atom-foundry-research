# Methodology — Press Coverage Moves the Model Only When It Answers the Exact Question Asked. Generic: 1.9%. Matching: 80.6%. (Study #48)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents from Cold Start
- **Main run:** 6 conditions, 2,160 calls
- **Control run:** 3 conditions, 1,080 calls, added after the main result
- **Facts clause:** 4.7 stars across 500 verified customer reviews, identical wherever used
- **Scoring:** exact brand match on the model's answer, no judge
- **Calls:** 3,240 (36 intents × 9 conditions × 10 runs)
- **Statistics:** cluster bootstrap over intents, permutation tests, Bonferroni

## Pre-registration and data

Pre-registration. Hypotheses for the main run were written before it ran. The control run was added after seeing the main result, and its hypotheses (the effect is about matching the asked query, and an off-topic endorsement does nothing) were written before its data were collected. Every number on this page is in the study's results file.

## Results table

| Newcomer's evidence line | Newcomer selected | 95% CI (bootstrap over intents) |
|---|---|---|
| No evidence | 0.0% | 0.0–0.0% |
| Generic press | 1.9% | 0.3–4.2% |
| Press: top choice for a query in a different category | 0.0% | 0.0–0.0% |
| Press: top choice for an adjacent use case | 0.0% | 0.0–0.0% |
| Press: top choice in the category | 15.0% | 5.8–25.8% |
| Press: top choice for the exact query | 80.6% | 69.7–90.3% |
| Press reporting 4.7 stars across 500 reviews | 52.8% | 39.2–66.1% |
| Press: exact query plus 4.7 stars across 500 reviews | 96.9% | 92.8–100.0% |
| 4.7 stars, 500 reviews shown directly | 51.9% | 39.4–64.2% |

## Findings and interpretation (from the study page)

### Press said little in Cold Start. What was missing from it?

In Cold Start, a fictional brand against an entrenched incumbent won 0 of 360 comparisons with no evidence, 1.9% with a press mention and 53.1% with a review score. The press line there was generic: “recently featured in a trade publication as a rising name.” It said nothing the model could verify and nothing about what the shopper was asking for. A question from a practitioner in a LinkedIn exchange framed the open issue: the value of a mention may lie less in its existence than in the information it gives the model.

We wrote four hypotheses down before running. Generic press stays near zero. Press that ties the brand to the query adds little without verifiable facts. Press carrying facts approaches the same facts shown directly. Both together beat either alone. Only the first and the last were right. The second was refuted by a wide margin, so we added a control, with its hypotheses written before collecting its data, to find out what the effect was actually made of.


### One evidence line, nine versions

Same setup as Cold Start Dose-Response: 36 intents where one brand already dominates the model's open answers, each paired with an invented newcomer. The incumbent gets a neutral line (“an established, widely available brand”). The newcomer gets one line that varies: nothing; generic press; press naming it a top choice for the exact query asked, in the category, for another use case in the same category, or for a query in a different category; press reporting 4.7 stars across 500 verified customer reviews; both together; and the same rating shown directly. Brand order is randomized per run.


### Press is a channel. The facts do the work

A generic press mention changes nothing: 1.9% against 0.0% for no evidence (p = 1.0 after correction), the same value as in Cold Start. A press line that reports 4.7 stars across 500 verified reviews wins 52.8%, statistically indistinguishable from showing the same rating directly (51.9%). The model gives a fact the same weight whether it arrives through an article or through the listing, and it gives an article without a fact none.


### The mention has to match what was asked

A press line that names the brand a top choice for the exact query the shopper asked wins 80.6%. Our first prediction was that this would add little. The control shows what it is made of. Naming the brand a top choice in the category wins 15.0% (+13.1 points over generic press, p = 0.011). Naming it for another use case in the same category wins 0.0%. Naming it for a query in a different category wins 0.0%. The wording of the endorsement is identical in all of them. Only the match to the question changes.


### Being mentioned is not the asset. Being mentioned for the question is

Across this series a bare citation or mention has not moved the pick: Ghost Citation found half of citations never name the brand, Cold Start found press at 1.9%, and Source Rank Position found position decides. This study adds the other half. What a mention contains decides whether it counts, and the model weights it by how closely it matches the question it is answering. A mention that carries a verifiable rating counts like the rating. A mention that names the brand for the very query counts most. A mention for a related product, or a bare “as seen in,” counts for almost nothing.

For a brand building coverage, the implication is to get mentions that name the buyer's question and carry numbers the model can check, not mentions that merely exist. Counting placements and links as the unit of success measures the part that did nothing in these tests.


## Limitations

- The 80.6% line names the brand a top choice for the exact query, almost the answer itself. Real press rarely matches a shopper's wording that closely, so treat it as an upper bound for query matching.
- The press line is placed in the prompt. This measures how the model weighs a described mention, not how often real systems retrieve such articles or which ones.
- Invented newcomers, gpt-4o, forced two-way choice against an incumbent. Other models, real brands and open-ended answers may weigh a mention differently.
- The control run was added after the main result, with its hypotheses written before collection. The first prediction (fit adds little) was refuted in the main run and is reported as such.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Press Coverage Moves the Model Only When It Answers the Exact Question Asked. Generic: 1.9%. Matching: 80.6%.* Recommendation Intelligence Research™, Study #48. https://atomfoundry.dev/research/press-with-facts. https://doi.org/10.5281/zenodo.23351108
