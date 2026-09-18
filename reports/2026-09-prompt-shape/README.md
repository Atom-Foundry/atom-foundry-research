# Prompt Shape

Atom Foundry — Recommendation Intelligence Research™ · Study #30
Published: 2026-09-12
DOI: [10.5281/zenodo.22758351](https://doi.org/10.5281/zenodo.22758351)

## Title

Ask Like You're Googling It, and the AI Recommends the Brand 15.6 Points Less

## Core finding

With the brand facts, named competitors, model, and system message held fixed, changing only how the buyer asks the question produced a repeatable winner-rate gap. The weakest length condition was the short `"best X"` phrase at **84.4%**, while the full natural question reached **100%**, a **15.6 percentage-point gap**.

A separate writer-persona test independently found the same weak point: Google-style bare-keyword phrasing scored **84.4%**, while four personas reached a 100% ceiling.

## Experiment

- Model: gpt-4o throughout.
- Brands: 4, spanning organic baby clothes, body piercing jewelry, Cuban-style hot sauce, and ceramic dinnerware.
- Length × sentence-type grid: 15 cells × 4 brands × 8 repeats = 480 calls.
- Persona layer: 7 personas × 8 templates × 4 brands = 224 calls.
- Total: 704 calls.
- Winner determination: gpt-4o LLM judge.
- Statistics: chi-square tests and logistic regression controlling for brand.
- The brand name never appears in the user's question. Brand facts and named competitors are carried in the fixed system message.

## Main results

### Length

| Length | Winner rate |
|---|---:|
| L1 bare keyword | 99.0% |
| L2 qualified phrase | 97.9% |
| L3 “best X” phrase | 84.4% |
| L4 full natural question | 100.0% |
| L5 paragraph with context | 91.7% |

The length effect was significant: χ²=32.29, p=0.000002.

### Sentence type

| Type | Winner rate |
|---|---:|
| Declarative | 98.8% |
| Question | 93.8% |
| Imperative | 91.2% |

Final LLM-judge result: χ²=9.11, p=0.011.

### Persona

| Persona | Winner rate |
|---|---:|
| Older man | 100.0% |
| Voice assistant | 100.0% |
| Young woman | 100.0% |
| Older woman | 100.0% |
| Neutral baseline | 93.8% |
| Young man | 90.6% |
| Google-style | 84.4% |

Persona effect: χ²=17.38, p=0.008.

## Scoring correction

The sentence-type result was re-evaluated after a bug was found in the original first-mention heuristic. The original method reported 95.6% / 86.9% / 74.4%; the rule-based re-score reported 87.5% / 82.5% / 76.2% and flipped the direction. The final scoring used an LLM judge asking whether the brand was the top recommendation, yielding 98.8% / 93.8% / 91.2%.

The final judge agreed with the original heuristic 90.1% of the time on the length grid and 90.5% on personas. The rule-based re-score agreed with the original method 85.4% of the time. Only the final LLM judge is treated as trusted scoring.

## Interpretation

The study does not show that a user's age or gender determines which brand an AI recommends. The persona prompts test writing style, not stated identity. The practical signal is the difference between bare search-bar phrasing and natural sentence phrasing.

The study also does not establish a universal effect across models or categories. It uses one model, four brands, one fixed system-message setup, and one round of 704 calls.

## Reproduction

The `experiment-summary.csv` contains the published aggregate metrics used in the charts. The `methodology.md` documents the experimental setup and scoring decisions. `Charts/` contains SVG visualizations of the final reported results.

## Citation

Atom Foundry (2026). *Ask Like You're Googling It, and the AI Recommends the Brand 15.6 Points Less* Recommendation Intelligence Research™, Study #30. Zenodo. https://doi.org/10.5281/zenodo.22758351
