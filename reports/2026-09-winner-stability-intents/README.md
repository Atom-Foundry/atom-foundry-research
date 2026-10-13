# Reword the Question Three Ways. The Winner Mostly Stays the Same.

Atom Foundry — Recommendation Intelligence Research™ · Study #40
Published: 2026-09-18
DOI: [10.5281/zenodo.22833586](https://doi.org/10.5281/zenodo.22833586)

## Headline result

Source Stability tested one thing: ask the identical question ten times, does the winning brand change. It mostly didn't. A LinkedIn reader pushed back with a different number, SparkToro's finding that two separate searches on the same topic return the same list less than 1% of the time, and argued that stability depends on wording, not on the model landing on a real, fixed pick. This study tests that objection directly: same eight product categories, but three differently worded questions per category, all carrying the same buying intent. Two independent rounds, 240 live search calls. The gap between how often the winner repeats on identical wording versus reworded wording was not statistically significant in either round on its own, and combined across both rounds it lands right at the edge of significance, p=0.063. Reformulating the question did not reliably flip the winner.

## Key figures

- **+3.1pp** — Combined cluster diff, borderline (p=0.063)
- **8** — Real product categories
- **240** — Live search calls, 2 rounds
- **98.8%** — Search invocation rate

## Design summary

- **Model:** gpt-4o, Responses API with web_search_preview
- **Categories:** 8, identical to Source Stability
- **Design:** 3 phrasings per category, 5 repeats each, 2 independent rounds
- **Total calls:** 480 (240 search, 240 judge extraction)
- **Winner extraction:** gpt-4o LLM judge on free text, identical prompt to Source Stability
- **Statistics:** per-category split by same-phrasing vs. different-phrasing pairs, cluster-permutation test across categories as primary evidence

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-same-phrasing-minus-different-phrasing-gap-by-category-both-.svg` / `.png` — Same-phrasing minus different-phrasing gap, by category, both rounds averaged

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/winner-stability-intents

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Reword the Question Three Ways. The Winner Mostly Stays the Same.* Recommendation Intelligence Research™, Study #40. Zenodo. https://doi.org/10.5281/zenodo.22833586
