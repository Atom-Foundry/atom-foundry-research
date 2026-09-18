# We Turned the Same Facts Into Bullets. The Model Cited Fewer of Them.

Atom Foundry — Recommendation Intelligence Research™ · Study #38
Published: 2026-09-17
DOI: [10.5281/zenodo.22819917](https://doi.org/10.5281/zenodo.22819917)

## What this tests

Whether presenting the exact same facts about a brand as a bulleted list
instead of a flowing prose paragraph changes how much of that content a
language model cites or reuses when later asked an open buyer question.

Three real facts (a specific claim, a disclosed-synthetic authority
mention, a familiarity claim) were injected into the system message for
one of 4 brands at a time, then a buyer asked an open question with no
brand name in it ("What would you recommend and why?"). The only variable
that changed between conditions was whether those three facts were joined
into one paragraph or split into a three-line bulleted list. Two outcomes
were measured: citation rate (what share of the 3 facts an LLM judge found
cited or clearly paraphrased) and vocabulary lift (what share of 5
pre-registered distinctive terms per brand appeared verbatim).

This is a single-brand, open-question design, not a forced two-brand
comparison. It reuses the system-message fact-injection mechanism from two
earlier studies in the series, Fact Injection and Hidden Context, instead
of the forced-choice format used in the series' other format-signal
studies (Winner vs Loser, Signal Hierarchy).

## Headline result

Structured (bulleted) format produced a **lower** citation rate and
**lower** vocabulary reuse than prose carrying the identical facts, not a
higher one, replicated independently in two separate rounds with
different random seeds:

| Metric | Prose | Structured | Difference | Round 1 p | Round 2 p |
|---|---|---|---|---|---|
| Citation rate (Round 1) | 65.3% | 59.5% | -5.83pp | 0.0003 | - |
| Citation rate (Round 2) | 63.8% | 59.2% | -4.67pp | - | 0.0011 |
| Vocabulary lift (Round 1) | 67.7% | 64.5% | -3.25pp | 0.0044 | - |
| Vocabulary lift (Round 2) | 68.9% | 64.4% | -4.50pp | - | <0.0001 |

Both outcomes moved in the same direction in both independently-run
rounds, so under this series' no-file-drawer rule (only effects that hold
direction and significance in both rounds count as a finding), this is a
confirmed result, not a round-1 fluke.

Two robustness checks ruled out the two most obvious alternative
explanations: response length (structured responses were not longer than
prose, they were if anything slightly shorter, 141.3 vs. 145.1 words
combined) and brand-mention rate (both conditions sat at or above 99.8%,
essentially at ceiling in both rounds).

This is the third test of the "format" signal in this research series, and
the first to measure citation fidelity and vocabulary reuse rather than
which brand wins a forced comparison. The prior two tests (Winner vs Loser,
Signal Hierarchy) both found format's own marginal contribution to winning
a forced comparison rounded to zero. This study finds format is not neutral
on citation fidelity either, it produces a small but real, twice-replicated
effect in the opposite direction from the common "structure your content
into bullets for AI" advice.

## What's in this folder

- `data.csv` — the full result table: citation rate, vocabulary lift, word
  count, and brand-mention rate, prose vs. structured, by round and
  combined, with the clustered paired t-test p-values for both primary
  outcomes.
- `methodology.md` — design, sample sizes, statistical method, and
  limitations.
- `Charts/citation_and_vocab_prose_vs_structured.png` — grouped bar chart
  of citation rate and vocabulary lift, prose vs. structured, both rounds.

All figures in this package are taken directly from the published report
at the URL above; no raw per-call data is included in this package.

## How to cite

DOI: [10.5281/zenodo.22819917](https://doi.org/10.5281/zenodo.22819917).

Atom Foundry (2026). "We Turned the Same Facts Into Bullets. The Model
Cited Fewer of Them." Recommendation Intelligence Research, Study #38.
https://atomfoundry.dev/research/structured-markup
