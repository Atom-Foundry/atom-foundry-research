# Methodology

## Research question

Does the shape of the buyer's question change which brand an AI system recommends when the brand facts and named competitors are held fixed?

## Design

The study uses two independent prompt-variation layers.

### Layer A — length × sentence type

Five length levels were crossed with three grammatical forms:

1. Bare keyword
2. Qualified phrase
3. “best X” phrase
4. Full question
5. Paragraph with context

Each was expressed as:

- declarative
- imperative
- question

This creates 15 cells. Each cell was run for four brands with eight repeats, for 480 grid calls.

### Layer B — writer-style personas

Seven prompt styles were tested, with eight different template phrasings per persona and all four brands:

- Neutral baseline
- Google-style
- Voice assistant
- Young woman
- Young man
- Older woman
- Older man

This creates 224 persona calls.

Total study volume: 704 calls.

## Fixed inputs

The model was gpt-4o throughout. For each brand, the system message carried the brand's real facts and real named competitors. The user question did not contain the brand name. The user prompt only described the shopping category, so changes in the winner were attributed to prompt shape rather than added brand claims.

The four brands span organic baby clothes, body piercing jewelry, Cuban-style hot sauce, and ceramic dinnerware. They were reused from Brand Legibility because their facts had already been verified.

## Measurement

Candidacy was measured with deterministic substring detection. Winner determination used a gpt-4o LLM judge rather than a position heuristic. The judge was asked whether the tested brand was the top recommendation.

The published aggregate candidacy rate is 97–100% across nearly every cell and persona. Therefore the substantive signal in this study is winner rate, not whether the brand was mentioned.

## Statistical analysis

The study reports chi-square tests for the length, sentence-type, and persona comparisons:

- Length: χ²=32.29, p=0.000002
- Sentence type: χ²=9.11, p=0.011
- Persona: χ²=17.38, p=0.008

A logistic regression controlling for brand confirms independent effects:

- Length effect: likelihood-ratio test p<0.00000001
- Persona effect: p=0.003

## Scoring correction

The first sentence-type result used a simple heuristic based on whether the brand's first mention occurred in the first 15% of the response. Manual inspection found that lead-in sentences before numbered lists could incorrectly penalize a brand that was genuinely ranked first.

A rule-based correction matched the original method 85.4% of the time and flipped the direction of the sentence-type result. Because neither heuristic was trusted, all responses were scored by the final gpt-4o LLM judge.

The original heuristic and final judge agreed 90.1% on the length grid and 90.5% on personas. The final judge is the trusted source for the published numbers.

## Limitations

- One model: gpt-4o.
- One fixed system-message setup.
- Four brands and a narrow category spread.
- One round of 704 calls.
- Persona prompts represent writing styles, not verified demographic behavior.
- The study did not test prompts that explicitly state the user's age or gender.
- The persona-by-brand interaction largely disappeared after the scoring correction.
- The findings should not be generalized to every model, category, or shopping situation without replication.

## Source

Atom Foundry, “Ask Like You're Googling It, and the AI Recommends the Brand 15.6 Points Less,” published September 12, 2026.
