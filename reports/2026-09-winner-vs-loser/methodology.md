# Methodology — Winner vs Loser (Study #33)

## Research question

When rating, claim specificity, and message format all vary at once, which signal actually decides an AI recommendation, and do the smaller signals hold up under replication?

## Design

Full 2x2x2 factorial per brand pair (8 conditions):

1. **Rating** — stronger rating and review count, assigned to target or competitor
2. **Specificity** — target's claim is vague or specific (competitor's claim held fixed as a plain, generic one-liner)
3. **Format** — one flowing paragraph versus a short, bulleted spec list

- Brands: Barbaro Mojo (functional), Hearthloom (functional), Colored Organics (trust), BodyArtForms (trust) — the same 4 brands used in the PDP Specificity study's original round
- 20 purchase intents x 5 repeats per cell
- 4 brands x 8 conditions x 20 intents x 5 repeats = 3,200 calls per round. 2 independent rounds, fresh random seed each = 6,400 calls total
- Model: GPT-4o throughout, single-turn, forced two-way pick, brand order randomized per call
- Winner determination: GPT-4o LLM judge, built in from the first run
- 0 parse failures across all 6,400 judge calls, both rounds

## Statistics

- Cluster-bootstrap confidence intervals over intents
- Per-round logistic regression for every factor and interaction
- One likelihood-ratio test on the full model as primary evidence: chi-square=5,572.16, df=7, p<0.0001 pooled (driven almost entirely by rating)
- 21 of 32 cells (4 brands x 8 conditions) sat near ceiling or floor in both rounds

## Results by factor (both rounds combined, n=3,200/level)

| Factor | Weaker level | Rate | Stronger level | Rate |
|---|---|---|---|---|
| Rating | Competitor stronger | 17.6% | Target stronger | 99.2% |
| Specificity | Vague | 55.5% | Specific | 61.3% |
| Format | Structured | 57.3% | Prose | 59.5% |

Specificity: p=0.0006 round 1, p=0.001 round 2 — holds the study's own replication bar. Format: pooled significance nudges to p=0.068 raw / p=0.014 controlling for word count, but this does not clear the bar in either round individually, so it is reported as unconfirmed, not as a finding.

## Category x specificity, by brand (both rounds combined)

| Brand | Category | Vague | Specific | Change |
|---|---|---|---|---|
| Barbaro Mojo | Functional | 71.5% | 79.0% | +7.5pp |
| Hearthloom | Functional | 50.2% | 58.5% | +8.3pp |
| Colored Organics | Trust | 50.0% | 54.8% | +4.8pp |
| BodyArtForms | Trust | 50.1% | 53.1% | +3.0pp |

Unlike the PDP Specificity study (where Colored Organics reversed, 93.5% to 85.0%, p=0.006), no reversal occurs here — Colored Organics goes up, not down. The interaction (category x specificity, pooled) is significant only when pooled (chi-square=4.02, df=1, p=0.045); round-by-round it does not replicate (chi-square=3.45, p=0.063 round 1; chi-square=0.96, p=0.328 round 2).

## Format word-count check

Structured messages averaged 58.9 words versus 54.9 for prose (consistent both rounds). Controlling for word count makes format's negative coefficient larger, not smaller (-0.093 uncontrolled to -0.128 controlled) — but neither round alone reaches significance, so the word-count check strengthens the case for caution rather than resolving it.

## Limitations

- Rating and review counts are synthetic but realistic, held fixed per brand — not scraped from a real product listing.
- This study tested 3 factors out of a longer list; price, authority, brand familiarity, and semantic positioning were deliberately left out and are covered by separate studies (Authority Signal, Brand Familiarity, signal-hierarchy).
- The category x specificity interaction and the format main effect are reported here as unconfirmed, not as proven-null.
- A convergence warning was noted in the logistic models, tied to how one-sided rating's effect is (near-total separation at ceiling/floor).
- A later study (Study #38, structured-markup) retests format specifically on citation fidelity and finds structured markup performs measurably worse than prose on that separate outcome.

## Data package note

`data.csv` in this package contains only the aggregate, published metrics shown on the live research page (https://atomfoundry.co/research/winner-vs-loser.html). No row-level or per-call model responses are included, consistent with Atom Foundry's data-sharing practice for this research series.
