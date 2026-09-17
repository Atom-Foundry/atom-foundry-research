# Methodology — Search Does Not Just Change Who AI Recommends. It Changes the Words It Uses.

## Research question

Does enabling web search change not only which brands gpt-4o recommends,
but the vocabulary it uses to describe them?

## Background

A companion study (Web Search Changes AI Recommendations) established that
77% of recommended brands change when web search is toggled on, versus a
23% overlap and a 39.1% noise-floor expectation. That study measured which
brands changed. This study reuses the same design to measure whether the
language itself changes, independent of which brand gets named.

## Design

- Same 50 buyer-intent prompts used in both conditions, spanning multiple
  ecommerce categories.
- Two conditions: web search enabled, web search disabled. Category and
  prompt set held identical across both.
- Model: gpt-4o.
- Word frequency counted separately in each condition's full set of
  responses, then normalized by total word volume in that condition. This
  removes the confound of search-on responses simply being longer.
- The frequency ratio for each word is (normalized frequency, search on) /
  (normalized frequency, search off).

## What is reported

The nine words with the largest ratio shifts are reported (`data.csv`).
This is a selection of the clearest signal, not an exhaustive account of
every word whose frequency changed between conditions.

## Supporting context

The noise-floor figures cited alongside this result (27% search on, 47%
search off — how often the model changes its own answer between repeat
runs with nothing else changed) are drawn from the companion browsing
study, reused here as corroborating context, not re-measured in this
analysis.

## Limitations

- Single model (gpt-4o), single-turn responses.
- Word-level frequency analysis does not capture semantic paraphrase; a
  word that shifts could still be under- or over-counting a concept
  expressed with different phrasing.
- The nine reported words were selected as the largest observed shifts,
  which is a form of selection on the outcome; they should be read as an
  illustration of the pattern, not as a pre-registered fixed word list.
- Results represent gpt-4o behavior at the time of testing and may not
  generalize to other models or change as models are updated.

## Data package

`data.csv` contains the nine word-frequency ratios, the noise-floor figures
from the companion study, the companion study's brand-change rate, and the
core design parameters. No row-level or per-call raw model responses are
included in this package; it contains published aggregate figures only.
