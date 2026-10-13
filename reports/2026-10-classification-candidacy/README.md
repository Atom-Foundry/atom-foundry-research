# Describe a Company by Its Side Feature and It Falls Off the AI Shortlist: 82.8% to 24.0%. The Model Still Names Its Category Correctly.

Atom Foundry — Recommendation Intelligence Research™ · Study #49
Published: 2026-10-13
DOI: [10.5281/zenodo.23351156](https://doi.org/10.5281/zenodo.23351156)

## Headline result

A claim circulates in AI-visibility work: when a secondary capability dominates the signals about a company, AI classifies the company by that capability and shortlists it wrongly, or leaves it out. We tested the outcome and the mechanism. The outcome is real and large. The mechanism is not what was claimed: the model names the company's core category correctly every time, and still shortlists it far less when the description is mostly about something else. Writing the primary category into the description did not repair it. What mattered was how much of the evidence is about the core, and whether it comes first.

## Key figures

- **82.8%** — Core leads
- **24.0%** — Side feature dominates
- **27.5%** — + "Primary category" line
- **100%** — Core category named

## Design summary

- **Model:** gpt-4o, temperature 0.7
- **Categories:** 20 invented B2B software categories, one target each
- **Task:** Name 3 of 12 companies for a buyer query, using only the descriptions shown
- **Round 1 (pilot):** 10 categories, 800 runs
- **Round 2 (main):** 20 categories, 1,200 runs, rivals written as richly as the target
- **Round 3 (follow-up):** 1,800 runs separating weight from order
- **Classification:** 1,800 forced-choice calls, six options, no judge
- **Statistics:** cluster bootstrap over categories, permutation tests, Bonferroni

## Package contents

- `README.md` — this file
- `methodology.md` — design, statistics, interpretation, and limitations
- `data.csv` — all published metrics from the live research page, machine-readable
- `Charts/01-target-company-on-the-3-name-shortlist.svg` / `.png` — Target company on the 3-name shortlist
- `Charts/02-target-company-on-the-3-name-shortlist.svg` / `.png` — Target company on the 3-name shortlist

## Source

Full write-up, methodology, and interactive charts: https://atomfoundry.dev/research/classification-candidacy

All figures in this package are pulled directly from the published, aggregate results on that page. No row-level or per-call model output is included.

## Citation

Atom Foundry (2026). *Describe a Company by Its Side Feature and It Falls Off the AI Shortlist: 82.8% to 24.0%. The Model Still Names Its Category Correctly.* Recommendation Intelligence Research™, Study #49. https://atomfoundry.dev/research/classification-candidacy. https://doi.org/10.5281/zenodo.23351156
