# Methodology

## Study

**The Model Hedges Most When It’s Most Sure**  
Study #22 · Published 2026-08-31

Source page: https://atomfoundry.dev/research/recommendation-confidence

## Design

The study reused the exact 16 fixed rating-signal scenarios from Candidate Evaluation so that the facts and correct pick stayed constant while measurement methods changed. Method 1 used a hedge/booster lexicon; method 2 used a blind Claude judge on 50 sampled texts; method 3 used constrained A/B token logprobs; method 4 requested 0–100 self-confidence; method 5 tested repetition stability across 10 runs; method 6 changed phrasing five ways; method 7 replicated the same scenarios across GPT-4o, Claude Sonnet 4.5 and Gemini 2.5 Flash. The HTML notes that hedge-rate percentages should be read directionally because exact lexicon labeling agreement was only 66%.

## Experimental parameters

- 16 identical fixed comparison scenarios
- ~2,900 calls across seven methods
- Primary model: gpt-4o, temperature 0.7 (methods 1–6)
- Cross-model replication: Claude Sonnet 4.5 and Gemini 2.5 Flash
- Ground truth for real confidence: OpenAI token logprobs
- Blind second-model judge for lexicon validation

## Primary outcomes

- Hedge language vs. real internal confidence: r=0.03.
- Rating-signal reasons had the highest hedge rate at 11.2%, even though rating produced the highest real confidence.
- Token-logprob confidence gaps were 82.3 for price, 88.2 for specs and 99.4 for rating.
- Self-reported confidence correlated only r=0.345 with real logprob confidence.
- 0 of 16 picks changed across five phrasing variants, while hedge rates changed substantially.
- All 16 intents had the same majority pick across GPT-4o, Claude and Gemini; within-model flip rates were 0%, 0% and 1.2%.
- Blind judge agreement with the lexicon was 66% on exact three-way labels and 76% on hedged-vs-not.

## Data handling and limitations

The methodology and limitations below are reproduced from the published HTML where stated. No additional experimental assumptions are introduced here. Values in the accompanying CSV are transcribed from the visible research page and its embedded chart labels.

## Reproducibility note

This repository package was reconstructed from the published Atom Foundry HTML page. It contains the study-level summary, the values explicitly exposed by the page, and charts regenerated from those published values. It does not claim to recreate any underlying raw model-response dataset that is not exposed in the HTML.
