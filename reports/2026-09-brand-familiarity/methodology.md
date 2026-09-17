# Methodology — Brand Familiarity (Study #35)

## Research question

Does a plain, unsourced claim that a brand is widely recognized change which brand an AI model recommends, first in isolation and then when a stronger rating signal is also present?

## Design

**Phase 1 — familiarity alone.** 2 conditions per brand pair: target has the familiarity claim, or competitor has it. No rating information present.

**Phase 2 — familiarity x rating, full 2x2.** 4 conditions per brand pair, crossing which brand carries the familiarity claim with which brand carries the stronger rating.

- Brands: Barbaro Mojo (functional), Hearthloom (functional), Colored Organics (trust/safety), BodyArtForms (trust/safety) — the same 4 brands used in the Authority Signal, PDP Specificity, and Winner vs Loser studies
- 20 purchase intents x 5 repeats per cell
- Phase 1: 4 brands x 2 conditions x 20 intents x 5 repeats = 800 calls
- Phase 2: 4 brands x 4 conditions x 20 intents x 5 repeats = 1,600 calls
- Total per round: 2,400 calls. 2 independent rounds, fresh random seed each = 4,800 calls total
- Model: GPT-4o throughout, single-turn, forced two-way pick, brand order randomized per call
- Winner determination: GPT-4o LLM judge, same judge prompt reused unchanged from the Winner vs Loser and Authority Signal studies
- 0 parse failures across all 4,800 judge calls, both rounds

## Statistics

- Phase 1: binomial test against 50% chance
- Phase 2: per-round logistic regression for main effects and the familiarity x rating interaction; one likelihood-ratio test on the full Phase 2 model as primary evidence (LR=1621.71 round 1, LR=1605.73 round 2, df=3, both p approx 0)
- Familiarity's marginal lift within the rating-disadvantaged condition moved by 0.4 points — smaller than the Authority Signal study's 1.5-point equivalent — and was not statistically distinguishable from chance under cluster-permutation

## Results by brand (Phase 1, both rounds combined, n=400/brand)

| Brand | Category | Follow-familiarity rate |
|---|---|---|
| Barbaro Mojo | Functional | 53.5% |
| Hearthloom | Functional | 81.8% |
| Colored Organics | Trust | 87.0% |
| BodyArtForms | Trust | 96.8% |

Barbaro Mojo's 53.5% is the closest any brand-signal combination has come to pure chance anywhere in this research series, and it landed at the identical value in both independent rounds (53.5% and 53.5%). Hearthloom, also a functional-category brand, still followed familiarity at 81.8% — so this is not a clean trust-versus-functional split.

## Limitations

- The familiarity claim is synthetic but disclosed as such, and is deliberately constructed to avoid naming any third party (that is the separate Authority Signal manipulation) or changing who a claim is attributed to (that is a separate claim-attribution manipulation).
- Only 4 brands were tested. One of them, Barbaro Mojo, responded to familiarity at barely above chance (53.5%, identical in both rounds) while the other three ranged from 81.8% to 96.8%.
- Single-turn, GPT-4o only, 5 repeats per cell.
- Phase 2's familiarity effect, where measurable, is very small (0.2 points) and should be read as "not confirmed," not as a proven null.
- A related, later study (Study #37, signal-hierarchy) puts familiarity head-to-head against three other non-rating signals; see that study for the cross-signal ranking.

## Data package note

`data.csv` in this package contains only the aggregate, published metrics shown on the live research page (https://atomfoundry.co/research/brand-familiarity.html). No row-level or per-call model responses are included, consistent with Atom Foundry's data-sharing practice for this research series.
