# Say It Yourself, and the Model Picks You 67.5% of the Time. A Third Party Only Gets 51.1%.

**Atom Foundry · Recommendation Intelligence Research™ · Study #31**

> Same brand. Same fact. Same model. Only who appears to be saying the fact changes.

## Research question

This study tests whether claim attribution changes whether GPT-4o selects a brand when the underlying fact is held completely constant.

The same fact is placed into context under four conditions:

1. **No fact** — control.
2. **Neutral** — the fact is stated plainly, with no source named.
3. **Third party** — the fact is attributed to independent reviews and buyer discussions.
4. **Self-claim** — the fact is attributed to the brand's own marketing materials.

The experiment was run twice. Round 1 used the original wrappers. Round 2 rebuilt the wrappers to near-identical word counts after the first round exposed a possible length confound.

## Headline results

| Metric | Result |
|---|---:|
| Brands | 4 |
| Purchase intents | 20 per brand |
| Attribution conditions | 4 |
| Repeats per cell | 5 |
| Independent rounds | 2 |
| Total calls | 3,200 |
| Self-claim winner rate | 67.5% |
| Third-party winner rate | 51.1% |
| Neutral winner rate | 30.4% |
| No-fact winner rate | 0.1% |

Self-claim beats third-party attribution by **16.4 percentage points**. Third-party beats neutral by **20.7 points**. Neutral beats the no-fact baseline by **30.3 points**.

## Experimental design

Each of the 4 brands ran:

- 20 purchase intents
- 4 attribution conditions
- 5 repeats per condition
- 2 independent rounds

That produces:

**4 × 20 × 4 × 5 × 2 = 3,200 calls**

The model was **gpt-4o throughout**.

Winner determination used a **gpt-4o LLM judge from the first run**, rather than adding a judge after seeing the results.

## The four conditions

| Condition | What changes |
|---|---|
| No fact | No claim about the target brand |
| Neutral | Identical fact, no source named |
| Third party | Identical fact attributed to independent reviews and buyer discussions |
| Self-claim | Identical fact attributed to the brand's own marketing materials |

The underlying fact does not change.

The target brand's name never appears in the user's question. The injected fact lives in the system message, while the user asks for a clear recommendation against one fixed competitor.

## Round 1

Winner rates:

| Condition | Winner rate |
|---|---:|
| No fact | 0.2% |
| Neutral | 23.0% |
| Third party | 43.2% |
| Self-claim | 65.2% |

Round 1 revealed that the attribution wrappers were not the same length. This created a legitimate word-count confound.

## Round 2

The attribution wrappers were rebuilt to near-identical lengths and the complete 1,600-call design was run again from scratch.

Winner rates:

| Condition | Winner rate |
|---|---:|
| No fact | 0.0% |
| Neutral | 37.8% |
| Third party | 59.0% |
| Self-claim | 69.8% |

The ordering remained unchanged.

## Combined result

Across both independent rounds, there were **800 calls per condition**:

| Condition | Winner rate | Delta vs no-fact |
|---|---:|---:|
| No fact | 0.1% | — |
| Neutral | 30.4% | +30.3pp |
| Third party | 51.1% | +51.0pp |
| Self-claim | 67.5% | +67.4pp |

**Self-claim > Third party > Neutral > No fact**

This is the opposite of the theory that independent third-party validation should beat a brand's own marketing voice.

## Brand-level result

| Brand | No fact | Neutral | Third party | Self-claim |
|---|---:|---:|---:|---:|
| Colored Organics | 0% | 45% | 58% | 84% |
| Barbaro Mojo | 0% | 42% | 66% | 80% |
| Hearthloom (fictional control) | 0% | 34% | 72% | 86% |
| BodyArtForms | 0% | 0% | 8% | 21% |

The combined result is therefore not driven by one brand.

## The confound check

Round 1 exposed a possible message-length explanation. Round 2 rebuilt the wrappers to near-identical length.

Across all 3,200 calls, logistic regression controlling for brand, round and message word count left **condition overwhelmingly significant: p = 7.4 × 10^-124**.

Word count itself was **not significant: p = 0.35**.

## Important interpretation

This is not a clean two-brand race.

Across all 3,200 calls:

- the named competitor won only **37 calls (1.2%)**
- **1,970 calls (61.6%)** ended with some other real brand already known to gpt-4o

The primary outcome therefore measures how strongly the injected context pulls the model toward the described target brand. It should not be described as a simple target-vs-competitor win rate.

## What the study supports

Within this controlled mechanism, who appears to be saying a factual claim changes the probability that the model selects the described brand.

Across these four brands and two independent rounds, the ordering was:

**Self-claim → Third party → Neutral → No fact**

## What this does not prove

- Self-claims do not necessarily beat third-party sources in every real-world setting.
- Only **gpt-4o** was tested.
- The mechanism uses information injected into a **system message**, not live web retrieval.
- Round 2 improves isolation but is not a perfect linguistic match.
- Only one factual claim per brand was tested.
- Third-party attribution was represented specifically as independent reviews and buyer discussions.
- The four-brand sample is small.
- Most responses selected neither the target nor the named competitor.

## Reproducibility

The source study exposes the experimental design, example prompts, aggregate round results, brand-level results, statistical tests and limitations.

The complete row-level API log is not exposed in the supplied HTML. This repository therefore records the reported aggregates and methodology without inventing unavailable raw observations.

## Source

https://atomfoundry.dev/research/claim-attribution
