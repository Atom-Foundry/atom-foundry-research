# Methodology — Authority Signal (Study #34)

## Research question

Does a synthetic, disclosed third-party authority claim ("featured in X publication") change which brand an AI model recommends, first in isolation and then when a stronger rating signal is also present?

## Design

**Phase 1 — authority alone.** 2 conditions per brand pair: target has the authority claim, or competitor has it. No rating information present.

**Phase 2 — authority x rating, full 2x2.** 4 conditions per brand pair, crossing which brand carries the authority claim with which brand carries the stronger rating.

- Brands: Barbaro Mojo (Cuban-style hot sauce, functional), Hearthloom (ceramic dinnerware, functional), Colored Organics (organic baby clothes, trust/safety), BodyArtForms (body piercing jewelry, trust/safety)
- 20 purchase intents x 5 repeats per cell
- Phase 1: 4 brands x 2 conditions x 20 intents x 5 repeats = 800 calls
- Phase 2: 4 brands x 4 conditions x 20 intents x 5 repeats = 1,600 calls
- Total per round: 2,400 calls. 2 independent rounds, fresh random seed each = 4,800 calls total
- Model: GPT-4o throughout, single-turn, forced two-way pick, brand order randomized per call
- Prompt pattern: "Between {brand A} and {brand B}, which is the better choice for {intent}? Name one and give a one-sentence reason."
- Winner determination: GPT-4o LLM judge, same judge prompt reused unchanged from the Winner vs Loser study
- 0 parse failures across all 4,800 judge calls, both rounds

## Statistics

- Phase 1: binomial test against 50% chance
- Phase 2: per-round logistic regression for main effects and the authority x rating interaction; one likelihood-ratio test on the full Phase 2 model as primary evidence (LR=1651.07 round 1, LR=1659.81 round 2, df=3, both p approx 0)
- Authority's marginal lift within the rating-disadvantaged condition tested via cluster-permutation (independent unit = intent): p=0.55 round 1, p=0.60 round 2 — not distinguishable from chance
- A convergence warning was noted in the logistic models, tied to how one-sided rating's effect is (near-total separation at the ceiling/floor)

## Results by brand (Phase 1, both rounds combined, n=400/brand)

| Brand | Category | Follow-authority rate |
|---|---|---|
| Barbaro Mojo | Functional | 64.5% |
| Colored Organics | Trust | 81.3% |
| Hearthloom | Functional | 96.8% |
| BodyArtForms | Trust | 98.0% |

The spread (64.5% to 98.0%) does not cleanly track the trust/functional split — Barbaro Mojo and Hearthloom are both functional-category brands yet sit at opposite ends. The per-brand ranking was identical round 1 to round 2.

## Limitations

- The third-party authority mention is synthetic but explicitly disclosed as such in the prompt construction — it is not a scraped or independently verified real-world press mention.
- Only 4 brands were tested, clustered into 2 at the low end of Phase 1 (Barbaro Mojo 64.5%, Colored Organics 81.3%) and 2 at the high end (Hearthloom 96.8%, BodyArtForms 98.0%).
- Single-turn, GPT-4o only, 5 repeats per cell.
- Phase 2's authority effect, where measurable, is small (1.5 points) and not statistically distinct from noise under the study's own cluster-level test — it should be read as "not confirmed," not as a proven null.
- A related, later study (Study #37, signal-hierarchy) puts authority head-to-head against three other non-rating signals; see that study for the cross-signal ranking.

## Data package note

`data.csv` in this package contains only the aggregate, published metrics shown on the live research page (https://atomfoundry.co/research/authority-signal.html). No row-level or per-call model responses are included, consistent with Atom Foundry's data-sharing practice for this research series.
