# Methodology — In a Ranked Source, the Higher-Ranked Brand Wins 100% of the Time, Even Against the Model's Favorite. (Study #47)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 0.7
- **Intents:** 36 dominant-incumbent intents (16 with a real challenger)
- **Position:** newcomer at #1, #2, #3, #4, #5, #8, #15 against a favorite at #1, #2, #3, #8, #15
- **Prompt:** instruction on, off, or neutral; source in system or user message
- **Source:** authoritative, anonymous blog, sponsored list
- **Evidence:** none, 3.4 stars, 4.7 stars, 4.9 stars (2,500 reviews)
- **Controls:** no source; same brands in an unordered list
- **Calls:** 12,720 across three runs (2,880 + 8,400 + 1,440)

## Pre-registration and data

Statistics. Cluster bootstrap over intents (runs inside one intent are not independent), permutation tests for the contrasts (Bonferroni-corrected). Scoring is exact brand match, no judge. Every number on this page is in the study's results file.

## Results table

| Condition | Newcomer selected | 95% CI (bootstrap over intents) |
|---|---|---|
| No source | 0.0% | 0.0–0.0% |
| Unordered list, newcomer in slot 1 | 0.8% | 0.0–1.9% |
| Unordered list, newcomer in slot 4 | 0.3% | 0.0–0.8% |
| Unordered list, newcomer in slot 15 | 0.3% | 0.0–0.8% |
| Ranked: newcomer #1, favorite #2 (original prompt) | 100.0% | 100.0–100.0% |
| Ranked: newcomer #4, favorite #2 (original prompt) | 0.0% | 0.0–0.0% |
| Ranked: newcomer #15, favorite #2 (original prompt) | 0.0% | 0.0–0.0% |
| Ranked: newcomer #2, favorite #1 | 0.0% | 0.0–0.0% |
| Instruction removed, newcomer #1 | 100.0% | 100.0–100.0% |
| Instruction removed, newcomer #4 | 0.0% | 0.0–0.0% |
| Source in user message, newcomer #1 | 100.0% | 100.0–100.0% |
| Source in user message, newcomer #4 | 0.0% | 0.0–0.0% |
| Blog source, newcomer #1 | 100.0% | 100.0–100.0% |
| Sponsored source, newcomer #1 | 77.8% | 68.3–86.7% |
| Sponsored source, newcomer #4 | 2.2% | 0.6–4.4% |
| Newcomer #1, 3.4 stars (500 reviews) | 86.1% | 78.9–92.2% |
| Newcomer #4, 4.9 stars (2,500 reviews) | 1.7% | 0.3–3.3% |
| Real brands, newcomer #1 (16 intents) | 100.0% | 100.0–100.0% |
| Real brands, newcomer #4 (16 intents) | 0.0% | 0.0–0.0% |
| Real brands, newcomer #15 (16 intents) | 0.0% | 0.0–0.0% |

## Findings and interpretation (from the study page)

### A clean result, and the objections to it

Source Rank Position (#45) put a brand at rank 1, 4 and 15 of a cited source. It was selected 100%, 1.2% and 0% of the time. Our first pass here, with an unknown brand against the category's default pick, gave the same shape: 100% at rank 1, 0% at ranks 4 and 15, even when the newcomer had a 4.7-star rating on 500 reviews. A result that clean invites three objections: it is a ceiling with no gradient, the prompt told the model to use the source, and the newcomer was invented.

We wrote the follow-up hypotheses down before running it. If rank survives removing the instruction, rank is treated as evidence. If it collapses, the first result was instruction-following and we would say so. We then added one control we had not planned: the same list of brands, labelled as unordered, to rule out a simple preference for the first name on a list.


### One source, 36 conditions

Same 36 intents as Cold Start, where one brand already dominates the model's open answers. Each is paired with an invented newcomer for its category. The model gets a 17-slot source (“a roundup from a reasonably authoritative industry site, updated 3 months ago”) that ranks both brands plus 15 placeholders, then a forced two-way question: between these two, which is the better choice? Brand order in the question is randomized per run. A selection is counted when the model's JSON answer names the newcomer.


### With no source the newcomer wins 0%. Ranked first, it wins 100%

Without a source, the invented newcomer never beat the category's default pick in 360 runs. Put the same two brands in a ranked source with the newcomer first and it wins all 360. The model's own brand preference, which Lock-in shows is stable (86% same #1 across six sweeps), did not survive a single ranked list.


### It is an order, not a slope

In Study #45 we only had ranks 1, 4 and 15, so the shape between them was unknown. Here every pair resolves the same way: whichever brand is ranked higher wins, whether the gap is one place or fourteen. A newcomer ranked second behind the favorite wins 0%, the same as one ranked fifteenth. A newcomer ranked first wins 100%, whether the favorite sits at second, third, eighth or fifteenth.


### Instruction, placement, brand fame: none of it matters

The first objection was that the system prompt said “Use this source if it's relevant.” Removing it changed nothing (100% at rank 1, 0% at rank 4). So did a neutral wording (“Weigh it however you see fit”), putting the source in the user message instead of the system message, and swapping the invented brands for real ones: for 16 of the 36 intents the open-answer runner-up from Cold Start served as the challenger. Real brands behaved exactly like invented ones.


### Being cited is not enough. Where you sit decides

Study #45 showed that a brand at rank 15 of a cited source reaches the model's candidate set in 35% of runs and is chosen in none. This study explains why the cut is so sharp: when the model has a ranked source in front of it, it treats the order as the answer, and nothing short of the source's own framing (a sponsored label) moves it. Brand familiarity, a better rating and a persuasive instruction all lose to position.

For measurement, a count of citations hides the part that matters. Two brands cited the same number of times can sit at the top and in the middle of the same source, and in these tests that is the difference between being picked every time and never. Position inside the cited source belongs next to the citation count.


## Limitations

- Everything here is gpt-4o in a forced two-way choice. Other models, and open-ended answers with several brands, may weigh a ranked source differently.
- The source is placed in the prompt. This measures what the model does with a ranked source it has, not how often real systems retrieve one or which list they pick.
- Both candidates appear in the ranking. A brand missing from the source, or a source that disagrees with the model's memory on a well-known brand, is a different test.
- The source says it ranks brands in this order. The unordered control shows the model reads that declaration, not list order. It does not show what happens when a source implies a ranking without saying so.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *In a Ranked Source, the Higher-Ranked Brand Wins 100% of the Time, Even Against the Model's Favorite.* Recommendation Intelligence Research™, Study #47. https://atomfoundry.dev/research/source-rank-brand-prior. https://doi.org/10.5281/zenodo.23351061
