# Methodology -- Two Signals Get You Most of the Way There

Reproduced from the published study page. All figures are aggregate
results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o throughout
- **Brands:** Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom (same 4 brands used across the "Recommendation Intelligence Research" sub-series)
- **Design:** 12 of the 16 possible on/off combinations of 4 non-rating signals (Authority, Familiarity, Specificity, Format), 20 purchase intents x 5 repeats, 2 independent rounds
- **Total calls:** 9,600 (4,800 per round)
- **Winner determination:** gpt-4o LLM judge, same judge prompt reused unchanged since Winner vs Loser
- **Statistics:** likelihood-ratio test, main effects plus all 2-way interactions, against an intercept-only null, computed per round
- **Task:** forced two-way pick, brand order randomized per call. Prompt: "Between {brand A} and {brand B}, which is the better choice for {intent}? Name one and give a one-sentence reason."

## The 12 conditions tested

1. **Baseline (0000)** -- nothing on, plain generic one-line description, prose format
2. **6 pairs** (AF, AS, AM, FS, FM, SM) -- exactly two of the four signals on
3. **4 leave-one-out triples** (drop-A, drop-F, drop-S, drop-M) -- three signals on, one held back
4. **Full stack (AFSM)** -- all four signals on at once

The 4 single-signal-alone cells were skipped on purpose; the study reuses
already-published solo numbers from Authority Signal (85.2%), Brand
Familiarity (79.8%), and PDP Specificity as reference points instead.

## Marginal contribution to the full stack (both rounds combined)

Full stack (AFSM) minus each leave-one-out condition. Positive = that
signal still helps once the other three are already present.

| Signal | Marginal contribution | Round 1 | Round 2 |
|---|---|---|---|
| Specificity | +3.25pp | +3.3pp | +3.2pp |
| Authority | +1.9pp | +2.0pp | +1.8pp |
| Familiarity | +0.9pp | +0.8pp | +1.0pp |
| Format | -0.1pp | -0.2pp | 0.0pp |

Specificity's solo main effect (on vs. off, pooled across all 12
conditions) is the largest of the four at +9.3 points (98.75% on vs. 89.45%
off). Authority and familiarity are close behind each other, roughly +5.5
to +5.9 points. Format's on/off gap is under 1 point (95.25% vs. 94.4%).

## Round 1 vs round 2 (selected conditions with a published round split)

| Condition | Round 1 | Round 2 | Combined |
|---|---|---|---|
| 0000 (baseline) | 76.5% | 74.5% | 75.5% |
| AS (authority+specificity) | 100.0% | 100.0% | 100.0% |
| drop-M (A+F+S, no format) | 100.0% | 100.0% | 100.0% |
| AFSM (full stack) | 99.8% | 100.0% | 99.9% |
| AM (authority+format, lowest pair) | 89.0% | 86.8% | 87.9% |

Position bias, target named first: 95.0% (R1) / 94.8% (R2). Target named
second: 94.7% (R1) / 95.1% (R2). No position bias worth naming.

## Robustness

- The originally specified full 4-way interaction model (16 parameters)
  failed to converge on round 1's data (quasi-complete separation from two
  conditions landing at exactly 100%). Fixed by reducing to main effects
  plus all 2-way interactions (11 parameters), the level this page's stats
  are reported at. Round 1 needed an L2-penalized fallback (LR=371.75,
  p=3.29e-77). Round 2 converged with plain MLE (LR=424.37, df=10,
  p=6.07e-85).
- 38 of 48 brand-by-condition cells landed above 95% or below 5% winner
  rate in both rounds, nearly the identical set both times.
- 0 judge parse failures across 9,600 calls, both rounds.

## Limitations (stated on the published page)

- All signal facts are synthetic (disclosed-synthetic authority mention,
  synthetic familiarity claim), not scraped from real press or real
  market-recognition data.
- Only 4 brands tested (2 trust-type, 2 functional-type); not a balanced
  design for testing whether category moderates any of this.
- The 12-condition subset deliberately skips the 4 single-signal-alone
  cells, reusing prior studies' published numbers as reference instead, so
  cross-study comparisons to those numbers are directional, not a strict
  apples-to-apples replication.
- The baseline itself (75.5%) sits well above a coin flip, a real
  structural asymmetry in this design.
- Single-turn, gpt-4o only, 5 repeats per cell.
- Price, brand fame beyond the familiarity claim tested here, and real
  (not synthetic) third-party mentions remain untested factors.
