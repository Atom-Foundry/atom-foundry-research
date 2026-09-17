# Specific Claims Add 15.7 Points in Spec-Driven Categories. They Cost Nearly 5 in Trust-Driven Ones.

Atom Foundry — Recommendation Intelligence Research™ · Study #32
Published: 2026-09-13
DOI: [10.5281/zenodo.22776560](https://doi.org/10.5281/zenodo.22776560)

## Headline result

Making brand language more concrete (vague marketing copy -> specific, PDP-style claims) does not have a uniform effect. Pooled across all 8 brands tested (n=600/condition):

- **Functional categories**: vague claims win 68.8% of comparisons, specific claims win 84.5% — a **+15.7 point** gain (p<0.0001)
- **Trust/safety categories**: vague claims win 65.2%, specific claims win 60.7% — a **-4.5 point** decline (not significant alone at this sample size, p=0.11; the category x specificity interaction controlling for brand across all 2,400 calls is significant, chi-square=39.26, df=1, p<0.0001)

In the original 4-brand experiment, the pooled winner rate rose from 54.1% (vague) to 62.9% (specific), replicated almost exactly across 2 independent rounds (54.2%/62.8% round 1, 54.0%/63.0% round 2).

## Design summary

- 8 ecommerce brands total: 4 original (Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom, tested across rounds 1-2) plus 4 added in round 3 (Wild One, Primally Pure, Bellroy, Zigpoll)
- 3 conditions: no claims (control), vague claims, specific PDP-style claims
- 20 purchase intents x 5 repeats per cell
- 3,600 total GPT-4o calls across 3 rounds (1,200 per round)
- Brand facts injected via a controlled system-message mechanism; the target brand's name never appears in the user's question
- GPT-4o LLM judge for winner determination, 0 parse failures out of 3,600 calls

## Package contents

- `README.md` — this file
- `methodology.md` — full method, statistics, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/three_condition_pooled_winner_rate.png` — no claims vs vague vs specific, original 4 brands
- `Charts/category_specificity_interaction.png` — the headline functional-vs-trust interaction, all 8 brands

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.co/research/pdp-specificity.html

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Specific Claims Add 15.7 Points in Spec-Driven Categories. They Cost Nearly 5 in Trust-Driven Ones.* Recommendation Intelligence Research™, Study #32. Zenodo. https://doi.org/10.5281/zenodo.22776560
