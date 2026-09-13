# Methodology

## Study metadata

- **Study:** The Model Knows 6 Facts About Your Brand. It Uses One
- **Study number:** #23
- **Published:** September 11, 2026
- **Model:** gpt-4o throughout
- **Brands:** 9
- **Possession calls:** 27
- **Deployment observations reused:** 3,600
- **Scoring calls:** approximately 280
- **Cells scored:** 308
- **Fact-cell pairs:** 1,392
- **Primary outcome:** possession-deployment gap rate
- **Confidence interval:** cluster bootstrap over brands
- **Correlation significance:** label-shuffle permutation test

## Research question

Does a fact a model can explicitly state about a brand actually appear when the model makes a real buyer-facing recommendation?

The design separates **possession** from **deployment**.

### Possession

The model is asked directly what it knows about a brand.

### Deployment

The possessed facts are checked against real recommendation responses where the brand is mentioned.

This makes the study a linkage test between what the model can retrieve when prompted and what it actually uses at the recommendation point.

## Phase 1 — Possession probe

Each of nine brands was tested in three fresh conversations.

The prompt asked gpt-4o for distinctive, checkable facts about:

- the brand
- its products
- pricing
- differentiators
- named competitors

The source describes the target as the most distinctive and checkable facts the model knows.

A fact was retained as a stable possessed fact only if it appeared in substance in at least two of the three runs.

This reduces the chance that a one-off generated phrase becomes part of the measured possession set.

## Phase 2 — Deployment dataset

The deployment side reuses already-collected Recommendation Reports data.

There are:

**400 real buyer-question observations per brand × 9 brands = 3,600 observations.**

The original observations contain the response text and whether the brand was mentioned.

Only observations where the brand was mentioned were eligible for fact-deployment scoring.

This avoids spending another ~3,600 model calls on data that already existed.

## Fact-cell scoring

Each eligible response was compared against the brand's possessed-fact list.

The question was:

> Does this specific possessed fact appear in this specific recommendation response, including a meaningful paraphrase?

The study reports:

- **308 cells scored**
- **1,392 fact-cell pairs checked**

The source describes approximately 280 new scoring calls, one per sampled mentioned cell.

## Primary calculation

For the full cohort:

**Deployment rate = deployed possessed-fact pairs / all checked possessed-fact pairs**

The source reports:

**Deployment = 24.2%**

Therefore:

**Gap rate = 100% − 24.2% = 75.8%**

95% CI for the gap:

**69.9–81.6%**

## Brand-level sampling

Most brands contribute 40 sampled mentioned cells.

Two brands have smaller samples:

- **Branch:** 23 cells
- **Zigpoll:** 5 cells

Zigpoll's 40% deployment estimate should therefore be treated as especially noisy. The source explicitly warns against interpreting that estimate alone.

## Topicals exclusion

Topicals was present in the underlying Recommendation Reports cohort but was mentioned in **0 of 400** buyer-question observations.

Because there are no mentioned responses, there is no deployment event to score.

The study excludes it from the possession/deployment cohort and identifies the situation as a Candidacy failure rather than a Linkage Gap.

## Relationship to recommendation frequency

The study also compares each brand's deployment rate with its published recommendation rate.

Reported result:

**r = -0.04, p = 0.91, n = 9**

This is a small-cohort diagnostic, not a definitive population-level null.

The interpretation is limited to:

> There is no visible relationship between deployment rate and recommendation rate in this nine-brand sample.

## Validation and self-grading risk

The same model family, gpt-4o, is involved in:

1. generating possession facts,
2. generating the deployment responses in the reused dataset,
3. judging whether facts appear in those responses.

This creates a genuine self-grading limitation.

The study describes an independent review of the scoring prompt before publication. The first scoring prompt was found to be too strict about wording and missed obvious paraphrases. One especially severe example produced 26 of 27 “no facts used” verdicts for one brand even though plain-text matches existed.

All **308 scored cells** were re-judged using a corrected prompt that explicitly allowed paraphrase matching.

The published numbers are from that corrected pass. fileciteturn60file0L642-L648

## Time separation

The deployment responses were collected approximately one to three weeks before the possession probe.

The data were therefore not paired in time.

The study assumes gpt-4o behavior did not materially shift in that interval, but this remains a design limitation.

## Statistical boundaries

The 75.8% headline is descriptive of the tested fact-cell sample.

The confidence interval is clustered over brands because multiple observations belong to the same brand.

The correlation analysis uses only nine brands and is explicitly underpowered.

No causal claim is made that a specific website change would necessarily increase deployment.

## Limitations

1. **Prompt-defined possession:** The extracted fact set depends on the possession prompt.
2. **Variable stable-fact count:** The source notes that the actual merged stable fact count ranged from 4–5 rather than being literally six for every brand.
3. **Reuse of deployment data:** Deployment responses were collected earlier and reused.
4. **Same-model scoring:** gpt-4o participates in generation and judging.
5. **Small cohort:** Nine brands.
6. **Uneven sampling:** Zigpoll has only five eligible cells.
7. **Single domain:** Consumer ecommerce.
8. **No causal manipulation:** This is a possession/deployment linkage study, not a controlled intervention.
9. **Cross-model generalization:** Not tested.
10. **Cross-platform generalization:** Not tested.

## Interpretation boundary

The strongest defensible statement is:

> Among the 1,392 possessed-fact pairs checked across nine ecommerce brands and real buyer-question recommendation responses, 75.8% of the facts the model could state when directly asked did not appear in the recommendation response where the brand was mentioned.

That establishes a large observed possession-to-deployment gap under this design.

It does not establish that the same percentage applies to every model, brand, category, prompt, or deployment context.
