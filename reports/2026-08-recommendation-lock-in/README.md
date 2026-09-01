# The Model Hedges Most When It’s Most Sure

Recommendation Intelligence Research™ · Atom Foundry · August 2026

---

# Research Summary

Candidate Evaluation showed what changes a contested recommendation. This study asks whether the model's verbal hedging tracks its actual confidence. Seven independent methods attack the question from different angles on the same 16 fixed scenarios.

---

# Research Question

Does hedged versus assertive language track a model's real confidence?

---

# Experimental Setup

- 16 identical fixed comparison scenarios
- ~2,900 calls across seven methods
- Primary model: gpt-4o, temperature 0.7 (methods 1–6)
- Cross-model replication: Claude Sonnet 4.5 and Gemini 2.5 Flash
- Ground truth for real confidence: OpenAI token logprobs
- Blind second-model judge for lexicon validation

---

# Key Findings

- Hedge language vs. real internal confidence: r=0.03.
- Rating-signal reasons had the highest hedge rate at 11.2%, even though rating produced the highest real confidence.
- Token-logprob confidence gaps were 82.3 for price, 88.2 for specs and 99.4 for rating.
- Self-reported confidence correlated only r=0.345 with real logprob confidence.
- 0 of 16 picks changed across five phrasing variants, while hedge rates changed substantially.
- All 16 intents had the same majority pick across GPT-4o, Claude and Gemini; within-model flip rates were 0%, 0% and 1.2%.
- Blind judge agreement with the lexicon was 66% on exact three-way labels and 76% on hedged-vs-not.

---

# Why It Matters

The wording around a decision is a poor proxy for the decision's internal confidence. The stable object is the choice itself and the facts supplied to the model, not whether the explanation sounds cautious or assertive.

---

# Dataset

- 16 fixed contested-pair scenarios
- ~2,900 calls
- 7 independent measurement methods
- 800 phrasing-perturbation calls
- 480 cross-model calls

---

# Methodology

The study reused the exact 16 fixed rating-signal scenarios from Candidate Evaluation so that the facts and correct pick stayed constant while measurement methods changed. Method 1 used a hedge/booster lexicon; method 2 used a blind Claude judge on 50 sampled texts; method 3 used constrained A/B token logprobs; method 4 requested 0–100 self-confidence; method 5 tested repetition stability across 10 runs; method 6 changed phrasing five ways; method 7 replicated the same scenarios across GPT-4o, Claude Sonnet 4.5 and Gemini 2.5 Flash. The HTML notes that hedge-rate percentages should be read directionally because exact lexicon labeling agreement was only 66%.

For the study-specific implementation details see:

`methodology.md`

---

# Related Research

- Hand It a Rating, and It Follows Every Single Time
- The Model Predicts Itself
- Two Months Later, the Model Still Agrees With Itself

---

# Resources

- `Charts/hedge-rate-by-signal.svg`
- `Charts/real-confidence-by-signal.svg`
- `Charts/hedge-rate-by-phrasing.svg`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

The wording around a decision is a poor proxy for the decision's internal confidence. The stable object is the choice itself and the facts supplied to the model, not whether the explanation sounds cautious or assertive.

Full write-up: https://atomfoundry.dev/research/recommendation-confidence

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
