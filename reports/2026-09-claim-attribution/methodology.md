# Methodology

## Study

**Title:** Say It Yourself, and the Model Picks You 67.5% of the Time. A Third Party Only Gets 51.1%.

**Study:** #31

**Series:** Recommendation Intelligence Research™

**Published:** 2026-09-12

**Source:** https://atomfoundry.dev/research/claim-attribution

## Research question

Does selection rate change based on who appears to be making a factual claim about a brand?

The underlying fact is held constant. Only its apparent attribution changes.

## Model and mechanism

- Model: **gpt-4o**
- Information mechanism: fact injection into the **system message**
- User question: matching-category purchase intent
- Target brand name: never appears in the user's question
- User prompt names one fixed established competitor and asks for a clear pick
- Winner determination: **gpt-4o LLM judge**, used from the first run
- Independent rounds: 2

The judge sees the response text, target brand and competitor, but not the experimental condition or round.

## Conditions

### 1. No fact

Control. No claim about the target brand is injected.

### 2. Neutral

The identical fact is stated in plain third-person language with no source named.

### 3. Third party

The identical fact is framed as something independent reviews and buyer discussions have noted.

### 4. Self-claim

The identical fact is framed as coming from the brand's own marketing materials.

The underlying factual statement remains the same.

## Experimental structure

Each of 4 brands ran:

- 20 purchase intents
- 4 conditions
- 5 repeats per condition
- 2 independent rounds

Total:

**4 × 20 × 4 × 5 × 2 = 3,200 calls**

Each round contains:

**4 × 20 × 4 × 5 = 1,600 calls**

## Round 1

Winner rates:

| Condition | Winner rate |
|---|---:|
| No fact | 0.2% |
| Neutral | 23.0% |
| Third party | 43.2% |
| Self-claim | 65.2% |

The attribution wrappers differed in length, creating a potential word-count confound.

## Round 2

The wrappers were rebuilt to near-identical length and the full 1,600-call experiment was run again from scratch.

Winner rates:

| Condition | Winner rate |
|---|---:|
| No fact | 0.0% |
| Neutral | 37.8% |
| Third party | 59.0% |
| Self-claim | 69.8% |

The ordering remained unchanged.

## Combined results

There are 800 calls per condition across both rounds.

| Condition | Winner rate |
|---|---:|
| No fact | 0.1% |
| Neutral | 30.4% |
| Third party | 51.1% |
| Self-claim | 67.5% |

## Brand-level results

| Brand | No fact | Neutral | Third party | Self-claim |
|---|---:|---:|---:|---:|
| Colored Organics | 0% | 45% | 58% | 84% |
| Barbaro Mojo | 0% | 42% | 66% | 80% |
| Hearthloom (fictional control) | 0% | 34% | 72% | 86% |
| BodyArtForms | 0% | 0% | 8% | 21% |

The study reports statistical significance for the attribution comparisons within each brand once both rounds are combined.

## Statistical tests

Reported pooled pairwise tests:

- Self-claim vs third party: **z = 6.67, p < 0.0001**
- Third party vs neutral: **z = 8.45, p < 0.0001**
- Neutral vs no fact: **z = 16.83, p < 0.0001**

Pooled chi-square:

- **χ² = 866.67**
- **df = 3**

Logistic regression controlling for brand, round and message word count:

- condition: **p = 7.4 × 10^-124**
- word count: **p = 0.35**

## Winner-rate interpretation

This is not a strict two-brand race.

Across all 3,200 calls:

- named competitor wins: **37 (1.2%)**
- other real brand wins: **1,970 (61.6%)**

The primary metric should therefore be interpreted as the pull of injected context toward the target brand, rather than a simple target-vs-competitor win rate.

## Limitations

1. Only gpt-4o was tested.
2. The mechanism is system-message fact injection, not live web retrieval.
3. Round 2 uses matched word counts but the wrapper grammar is not perfectly identical.
4. Round 2 uses third-person self-claim wording to isolate attribution.
5. Only one factual claim per brand was tested.
6. Third-party attribution is represented by independent reviews and buyer discussions.
7. Most responses selected neither the target nor the named competitor.
8. The four-brand sample is small.
9. The row-level API dataset is not exposed in the supplied HTML.

## Data boundary

This package records aggregate results explicitly reported by the study. It does not reconstruct or invent unavailable row-level API observations.
