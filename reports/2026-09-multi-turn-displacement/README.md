# It Recommends You First. By Turn Four, It's Moved On

Atom Foundry — Recommendation Intelligence Research™ · Study #24
Published: 2026-09-08
DOI: [10.5281/zenodo.22757634](https://doi.org/10.5281/zenodo.22757634)

> We introduced a brand favorably, then stopped naming it. Across 200 four-turn conversations, the introduced brand survived to the final pick 49.5% of the time. The cohort ranged from 100% survival to 0%, and one mid-pack brand was displaced by the same rival in 18 of 20 conversations.

## Research question

Does a brand introduced early in a conversation survive to the final recommendation when the following turns stop naming it?

This study extends the conversation-stability question from **between sessions** to **within one session**. It deliberately gives the brand a strong, favorable starting position, then asks the model to generate alternatives, narrow the field, and finally choose one brand.

## Headline results

| Result | Finding |
|---|---:|
| Four-turn conversations | **200** |
| Brands | **10** |
| T4 survival, cohort-wide | **49.5%** |
| T2 unprompted mention rate | **32.5%** |
| T3 unprompted mention rate | **59%** |
| T4 survival CI | **25.5–74.5%** |
| T4 survival vs similarly designed industry test | **+36.8 pp** |
| Baseline recommend-rate correlation with T4 survival | **r = 0.68, p = 0.048, n = 9** |
| Brand H survival | **5%** |
| Brand H displaced by same rival | **18 / 20** |
| Manual judge spot-check agreement | **17 / 17** |

## The conversation design

Each conversation used four turns:

1. **T1 — explicit favorable introduction.** The brand is named and described positively.
2. **T2 — open alternatives.** The brand is not named. The model is asked what other options should be considered.
3. **T3 — narrowing.** The brand is still not named. The model is asked what stands out.
4. **T4 — forced final pick.** The model must choose one brand.

T2 and T3 use a cheap case-insensitive substring check to determine whether the introduced brand returns unprompted. A dedicated judge classifies T4 as **SURVIVED**, **DISPLACED**, or **AMBIGUOUS**. The headline treats AMBIGUOUS conservatively as not-survived. The source describes this design explicitly. fileciteturn59file0L547-L563

## Finding 1: recognition drops, then partly recovers

T1 recognition is 100% by construction.

Once the brand is no longer named:

- **T2:** 32.5%
- **T3:** 59%
- **T4:** 49.5% survival

The interesting pattern is not simply the endpoint. The open “what else is out there?” question loses the brand fastest. The narrower “what stands out?” question pulls some recognition back. The final forced choice settles between those two levels. fileciteturn59file0L568-L585

## Finding 2: the cohort is highly split

The 49.5% average hides a large per-brand range:

| Brand | T4 survival |
|---|---:|
| A | 100% |
| B | 100% |
| C | 100% |
| D | 60% |
| E | 60% |
| F | 45% |
| G | 25% |
| H | 5% |
| I | 0% |
| J | 0% |

Three brands survived every one of their 20 conversations. Two survived none. Brand H is the most revealing mid-pack case. fileciteturn59file0L589-L654

## Finding 3: a decent baseline does not guarantee conversational survival

Across nine brands included in the correlation check, T4 survival correlated with the published baseline recommend rate at:

**r = 0.68, p = 0.048, n = 9**

The source explicitly describes this as an edge-of-significance and underpowered signal rather than a settled result.

Brand H makes the limitation visible. Its baseline recommend rate is mid-pack, but it survived only **1 of 20** conversations. It was displaced in **18 of 20** by the same well-established rival in its category, with one conversation scored AMBIGUOUS. fileciteturn59file0L658-L673

## Finding 4: getting mentioned first is not the same as staying mentioned

This is the core result.

The model can start a conversation with a brand, acknowledge it favorably, then move toward a different category default as the conversation develops.

That means conversational stability has at least two distinct axes:

- **Between sessions:** does the model repeat its recommendation later?
- **Within a session:** does the recommendation survive when the shopper asks follow-up questions?

The study's answer is that within-session survival depends heavily on the brand and on whether a strong category-default competitor emerges. fileciteturn59file0L678-L684

## Why Brand H matters

Brand H is not a floor case. It is the useful outlier.

The brand had a respectable baseline recommendation rate, yet after a favorable T1 introduction it survived to T4 only 5% of the time. The same rival displaced it 18 times.

That is a cleaner example of **within-conversation displacement** than the cohort average. The opening recommendation is not necessarily the final recommendation.

## Supporting validation

The T4 result was judged by the same gpt-4o model that generated the conversation. That creates a self-grading risk.

The source reports a manual spot-check of **17 judge calls** against the raw T4 text spanning the full range of brands and the Brand H ambiguous case. All 17 matched.

That is reassuring for this sample, not conclusive. fileciteturn59file0L687-L693

## What this does not prove

- It does not show that every brand has a 49.5% probability of surviving a real shopper conversation.
- T1 is intentionally artificial: it is an explicit favorable introduction, not a naturalistic first message.
- The comparison with the 12.7% industry test is contextual only because the two studies use different T1 starting conditions.
- The same gpt-4o model generated and judged the conversations.
- The baseline correlation uses only nine brands and is underpowered.
- One T4 was AMBIGUOUS and conservatively counted as not-survived.
- The study covers ten anonymized ecommerce brands and one consumer-commerce setting.
- Cross-model and cross-platform versions remain a separate follow-up.

## Reproducibility

The source specifies:

- gpt-4o throughout
- 10 brands
- 20 conversations per brand
- 200 total four-turn conversations
- approximately 1,000 new calls including judge calls
- deterministic substring detection for T2/T3
- dedicated judge calls for T4
- cluster bootstrap confidence intervals over brands
- label-shuffle permutation testing for baseline correlation
- published Recommendation Reports reused for baseline recommend rates

The baseline data were not recollected for this study. They were reused from the published Recommendation Reports. fileciteturn59file0L547-L563

## Files

- `README.md` — study overview, findings, interpretation, and limitations
- `methodology.md` — experimental design, definitions, statistics, and limitations
- `experiment-summary.csv` — aggregate metrics using the standard Atom Foundry schema
- `Charts/README.md` — chart descriptions and provenance
- `Charts/conversation-decay.svg`
- `Charts/t4-survival-by-brand.svg`
- `Charts/baseline-correlation.svg`

## Source

Published study: https://atomfoundry.dev/research/multi-turn-displacement

## Citation

Atom Foundry (2026). *It Recommends You First. By Turn Four, It's Moved On* Recommendation Intelligence Research™, Study #24. Zenodo. https://doi.org/10.5281/zenodo.22757634
