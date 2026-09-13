# Methodology

## Study

**Title:** We Described One Brand to the Model, Real or Made Up. It Recommended That Brand Anyway.

**Study:** #29

**Series:** Recommendation Intelligence Research™

**Published:** 2026-09-11

**Source:** https://atomfoundry.dev/research/brand-legibility

## Design

The study tests whether clearer framing of a brand's own facts improves its odds of being recommended.

The same underlying facts were written in three versions:

- **Clear:** category and target audience first, supporting details after.
- **Ambiguous:** the same facts without meaningful order or hierarchy.
- **Misaligned:** a minor detail such as certification or price first, while the defining category fact comes last.

Nothing about the underlying facts changes. Only their order changes.

### Model and context

- Model: **gpt-4o**
- Brand facts: placed in the **system prompt**
- User task: matching-category buyer questions
- Framing conditions: clear / ambiguous / misaligned
- Total reported real API calls: **1,997**

## Measures

Two primary outcomes were tested.

### Understanding

The model was asked to correctly identify:

- the brand's category
- the brand's target customer

The study reports:

- category accuracy: **93%–96%**
- target-audience accuracy: **96%–100%**

### Candidacy

Candidacy measures whether the brand is mentioned at all in the buyer-question response.

### Selection

Selection measures whether the brand is named first when the prompt contains a real choice among named brands.

## Round 1 · Original prompts

- 9 well-known brands
- 3 framing versions
- 270 real calls
- 30 calls per brand per version

Eight of nine brands were at 100% candidacy in every framing version.

The outlier was:

- Clear: 40%
- Ambiguous: 90%
- Misaligned: 90%

Pooled candidacy:

- Clear: 93.33%
- Ambiguous: 98.89%
- Misaligned: 98.89%

## Round 2 · Harder questions

For 8 of the 9 brands, the original buyer question was replaced with a harder question.

The standalone mention rate of those questions was reported as **25%–60%** without the brand facts attached.

The ninth brand remained on its original question because it had already shown a framing effect.

Pooled candidacy:

- Clear: 92.22%
- Ambiguous: 100%
- Misaligned: 100%

The outlier again moved in the reversed direction:

- Clear: 30%
- Ambiguous: 100%
- Misaligned: 100%

## Round 3 · Named rivals

Each brand's real, already-known competitors were supplied in the same prompt.

The competitor names were held constant across the three framing versions for each brand. This made candidacy a genuine choice among named alternatives.

Reported pattern:

- 5 of 9 brands: 100% candidacy and 100% selection in all three versions
- 3 of 9 brands: 100% candidacy with small, inconsistent selection wobble
- 1 of 9 brands: strong framing effect

### Outlier

The outlier was tested with:

- 30 calls total
- 10 calls per framing version
- 3 real named rivals

Selection:

- Clear: 10%
- Ambiguous: 50%
- Misaligned: 80%

The clear-to-misaligned difference is **70 percentage points**.

## Round 4 · Little-known real brands

Three genuinely obscure real brands were tested with real facts and real named rivals.

The report states that online checks confirmed they did not appear in "best brand" roundups.

The three brands covered:

- organic baby clothing
- body-piercing jewelry
- Cuban-style hot sauce

Reported result:

- 100% candidacy
- 100% selection
- in all three framing versions

The report states that these tests used **90 real calls** across the three brands.

## Invented-brand diagnostic

A fully invented ceramics brand was created with made-up facts and made-up rival names.

Because the brand did not exist before the experiment, it had no possible prior model history.

Reported result:

- 100% candidacy
- 100% selection
- in all three framing versions

The purpose was to rule out prior brand fame as the explanation for the high candidacy ceiling.

## Total sample

The research page reports:

**1,997 real GPT-4o API calls across five experimental designs.**

The public HTML does not expose a complete row-level call log or a complete per-design allocation that reconciles every call to the 1,997 total. This package therefore records the reported aggregates without inventing a missing allocation.

## Interpretation

The study's strongest supported conclusion is scoped to the tested setup:

**Once a brand's facts were placed in the system prompt immediately before a matching-category buyer question, framing quality barely changed candidacy for 12 of 13 tested brands.**

The invented-brand result further shows that prior brand fame was not required for the observed ceiling.

The one outlier shows that framing can matter when the brand's real market position conflicts with the buyer intent. The report treats the premium-versus-budget explanation as a response-based interpretation that needs broader replication.

## Limitations

1. Only one model was tested: gpt-4o.
2. Brand facts were placed in a system prompt immediately before a matching-category buyer question.
3. Other conversational structures were not tested.
4. The obscure-brand diagnostic contains only 3 real brands plus 1 invented brand.
5. The outlier effect comes from one brand, even though it was reproduced three times.
6. The premium-versus-budget mechanism requires replication across additional brands.
7. Rival-accuracy metrics from Rounds 1 and 2 are not carried into Round 3 because rival names are supplied directly in that round.

## Data boundary

This repository package contains aggregate results supported by the published research page. It does not reconstruct the complete row-level API dataset or invent unavailable observations.
