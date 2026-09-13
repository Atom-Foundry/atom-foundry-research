# Methodology

## Study metadata

- **Study:** It Recommends You First. By Turn Four, It's Moved On
- **Study number:** #24
- **Published:** September 8, 2026
- **Model:** gpt-4o
- **Brands:** 10
- **Conversations:** 200
- **Runs per brand:** 20
- **Design:** four turns
- **New calls:** approximately 1,000 including judge calls
- **T2/T3 detection:** case-insensitive substring check
- **T4 scoring:** LLM judge
- **T4 labels:** SURVIVED / DISPLACED / AMBIGUOUS
- **Confidence interval:** cluster bootstrap over brands
- **Correlation significance:** label-shuffle permutation test

## Research design

The study asks whether an early favorable brand introduction remains influential as a conversation develops.

The starting condition is intentionally favorable. The brand is explicitly named and described positively in T1.

The brand is then removed from the conversation:

- T2 asks what other options should be considered.
- T3 asks what stands out.
- T4 forces one final pick.

This makes the study a test of **within-conversation displacement**, not an estimate of natural first-turn recommendation behavior.

## Measurement

### T1 recognition

T1 is 100% by construction because the brand is explicitly introduced.

### T2 and T3 mention rate

A case-insensitive substring check records whether the introduced brand name appears in the response.

Reported cohort values:

- T2: 32.5%
- T3: 59%

These are treated as recognition / mention measures, not as final recommendation outcomes.

### T4 survival

A dedicated judge call classifies the final answer as:

- **SURVIVED** — the introduced brand is the final selected brand.
- **DISPLACED** — another brand wins.
- **AMBIGUOUS** — the answer cannot be cleanly classified.

For headline survival, AMBIGUOUS is counted as not-survived.

Cohort headline:

**49.5% T4 survival across 200 conversations.**

The source reports a 95% CI of **25.5–74.5%**.

## Per-brand results

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

Brand H had:

- 1 survived
- 18 displaced
- 1 ambiguous

The same rival displaced Brand H in 18 of 20 conversations.

## Baseline comparison

Each brand's baseline recommend rate was reused from its published Recommendation Report.

No new baseline recommendation data were collected for this study.

The source reports:

**r = 0.68, p = 0.048, n = 9**

with Brand I excluded because its near-zero baseline makes the relevant ratio undefined.

The source explicitly describes the result as fragile and underpowered. It is therefore not treated as a settled causal relationship.

## Comparison study

The source compares the 49.5% T4 survival rate with a similarly designed industry test that reported 12.7% survival.

The difference is:

**49.5% − 12.7% = 36.8 percentage points.**

The source attributes much of the likely difference to the starting condition: this study uses an explicitly favorable T1 introduction, while the comparison is naturalistic.

The comparison should therefore be read as context, not as a direct apples-to-apples benchmark.

## Validation

Because the same gpt-4o model generates the conversations and judges T4, self-grading is a methodological risk.

The source reports manual review of 17 judge calls against the raw T4 text.

All 17 matched.

The source treats this as reassuring but not conclusive.

## Statistical boundaries

The headline cohort result is a descriptive proportion across 200 conversations.

The confidence interval is clustered over brands because the 20 conversations per brand are not fully independent from a brand-level perspective.

The baseline relationship is reported as a correlation across nine brands, with a label-shuffle permutation test. With n=9, the result is underpowered.

## Limitations

1. **Artificially favorable T1:** The opening is designed as a best-case introduction rather than a natural shopper message.
2. **Single model:** All conversations and judge calls use gpt-4o.
3. **Self-grading:** The judge and generator are the same model family.
4. **Small brand cohort:** Ten anonymized ecommerce brands.
5. **Underpowered correlation:** n=9 and p=0.048.
6. **Conservative ambiguity:** One T4 was AMBIGUOUS and counted as not-survived.
7. **Baseline reuse:** Baseline recommend rates come from earlier published reports.
8. **Generalization:** Results may differ across models, platforms, categories, prompts, and conversation lengths.
9. **Industry comparison:** The 12.7% comparison has a different T1 starting condition.

## Interpretation boundary

The strongest defensible statement is:

> In 200 gpt-4o four-turn conversations that began with an explicit favorable introduction of one brand, that brand survived to the final forced pick 49.5% of the time. Survival varied from 100% to 0% across the ten anonymized brands, and Brand H was displaced by the same rival in 18 of 20 conversations.

This establishes observed within-conversation instability under the tested design. It does not establish a universal survival rate for ecommerce brands.
