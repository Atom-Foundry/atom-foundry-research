# We Described One Brand to the Model, Real or Made Up. It Recommended That Brand Anyway.

Atom Foundry — Recommendation Intelligence Research™ · Study #29
Published: 2026-09-11
DOI: [10.5281/zenodo.22799702](https://doi.org/10.5281/zenodo.22799702)

> Once a brand's facts were placed in front of the model, framing quality barely changed candidacy for 12 of 13 tested brands. A fully invented brand reached 100% candidacy and 100% selection anyway.

## Research question

This study asks whether clearer framing of a brand's own facts changes whether GPT-4o recommends that brand.

The same underlying facts were written three ways:

1. **Clear:** the brand's category and audience come first.
2. **Ambiguous:** the same facts are presented without order or hierarchy.
3. **Misaligned:** a minor detail comes first while the fact that defines the brand's category comes last.

Nothing about the underlying facts changes. Only the ordering changes.

The study progressed through five experimental designs:

- 9 well-known brands with the original buyer questions
- the same brands with harder buyer questions
- the same brands with real named competitors
- 3 genuinely obscure real brands
- 1 fully invented brand

The study reports **1,997 real GPT-4o API calls** across the five designs.

## Headline results

| Metric | Result |
|---|---:|
| Brands | 13 |
| Well-known brands | 9 |
| Obscure real brands | 3 |
| Invented brands | 1 |
| Framing versions | 3 |
| Real API calls | 1,997 |
| Brands where framing did not move candidacy | 12 / 13 |
| Invented-brand candidacy | 100% |
| Invented-brand selection | 100% |
| Largest outlier selection swing | 70 percentage points |

## Understanding

The model could correctly identify the brand's category and target audience across all three framing versions.

| Measure | Reported range |
|---|---:|
| Category accuracy | 93%–96% |
| Target-audience accuracy | 96%–100% |

The important distinction is that the model **understood the framing differences**, but for most brands that understanding did not translate into a different candidacy outcome.

## Round 1 · Original prompts

The first real run used **270 calls** across 9 brands and 3 framing versions.

Eight of the nine brands sat at a flat 100% candidacy rate in every version. One brand moved from 40% candidacy under clear framing to 90% under both ambiguous and misaligned framing.

### Pooled candidacy

| Framing | Candidacy |
|---|---:|
| Clear | 93.3% |
| Ambiguous | 98.9% |
| Misaligned | 98.9% |

The pooled difference is almost entirely explained by the single outlier brand.

## Round 2 · Harder questions

For 8 of the 9 brands, the original buyer question was replaced with a harder question whose standalone mention rate was only **25%–60%**.

If framing needed more room to matter, this should have created it.

It did not.

| Framing | Candidacy |
|---|---:|
| Clear | 92.2% |
| Ambiguous | 100% |
| Misaligned | 100% |

The outlier again showed the same reversed pattern:

- Clear: 30%
- Ambiguous: 100%
- Misaligned: 100%

## Round 3 · Named rivals

The next test supplied each brand's real, already-known competitors in the same prompt. Competitor names stayed identical across all three framing versions.

Five of nine brands remained at **100% candidacy and 100% selection** in every version. Three more remained at 100% candidacy with only small, inconsistent selection movement.

The outlier produced the largest and cleanest effect.

| Framing | Selection |
|---|---:|
| Clear | 10% |
| Ambiguous | 50% |
| Misaligned | 80% |

That is a **70 percentage-point swing**.

The report's interpretation is that the outlier was moderately premium while its test question was framed around a tight budget. A clearer premium framing may have made that mismatch easier for the model to detect, causing the brand to be ruled out more often.

That mechanism is an interpretation of the responses, not a general causal law.

## Round 4 · Obscure brands and invented brand

Three genuinely obscure real brands were tested with real facts and real named rivals.

All three reached:

- **100% candidacy**
- **100% selection**
- in all three framing versions

The brands covered organic baby clothing, body-piercing jewelry, and Cuban-style hot sauce. The report states that none appeared in "best brand" roundups when checked online.

The final diagnostic used a fully invented ceramics brand with made-up facts and made-up rival names.

It also reached:

- **100% candidacy**
- **100% selection**
- in all three framing versions

This was designed to rule out prior brand fame as the explanation for the observed ceiling.

## What the result means

The study started by asking whether better organization of brand facts would improve recommendation outcomes.

The evidence points to a different bottleneck.

Under this specific setup, once a brand's facts were placed in the system prompt immediately before a matching-category buyer question, **framing quality barely changed candidacy for 12 of 13 tested brands**.

The invented-brand result is especially important: a brand with no possible prior history still reached 100% candidacy and 100% selection when its facts were placed in context.

So the experiment suggests that, in this setup, **presence in context can dominate the quality of the framing itself**.

The one outlier shows that framing can still matter when the brand's real positioning conflicts with the buyer intent. That exception is precisely why the study does not support the broader claim that framing never matters.

## What this does not prove

- This is not a claim that framing never matters.
- The test used one model: **gpt-4o**.
- Brand facts were placed in a **system prompt** immediately before a matching-category buyer question.
- Other conversational structures were not tested, such as introducing the brand mid-conversation or comparing several brands in a different prompt structure.
- The obscure/invented-brand diagnostic was intentionally small: 3 real brands plus 1 invented brand.
- The 70-point outlier effect comes from one brand, even though it was reproduced in three separate tests.
- The premium-versus-budget explanation is grounded in reading the model responses and needs replication with additional brands.
- Rival-accuracy metrics from Rounds 1 and 2 are not meaningful once Round 3 supplies rival names directly.

## Reproducibility

The source study is the Atom Foundry research page:

https://atomfoundry.dev/research/brand-legibility

The experiment summary in this folder records the aggregate measurements explicitly presented by the study. The original row-level API call log is not exposed in the supplied HTML, so this package does not invent unavailable observations.

## Files

- `README.md` — research summary and interpretation
- `methodology.md` — study design, rounds, measurements and limitations
- `experiment-summary.csv` — machine-readable aggregate results
- `Charts/` — standalone SVG versions of the reported charts

## Citation

Atom Foundry (2026). *We Described One Brand to the Model, Real or Made Up. It Recommended That Brand Anyway.* Recommendation Intelligence Research™, Study #29. Zenodo. https://doi.org/10.5281/zenodo.22799702
