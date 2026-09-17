# Search Does Not Just Change Who AI Recommends. It Changes the Words It Uses.

Atom Foundry Research · Recommendation Intelligence Research™ series · Study #5
Published: July 2026

## Headline result

The companion browsing study already established that turning search on
changes 76.9% of the brands GPT-4o recommends, far above the 39.1% expected
from noise alone. This study holds the same 50 prompts and categories
constant across both conditions and asks a narrower question: does search
also change the *words* the model uses, not just the names?

It does. With search on, the model's language shifts toward composition and
specification terms. With search off, it falls back on general, unverifiable
impression language.

| Word | Frequency ratio (search on / search off) | Tier |
|---|---:|---|
| monohydrate | 21.0x | Strong shift |
| provides | 20.0x | Strong shift |
| whey | 17.0x | Strong shift |
| leggings | 15.0x | Strong shift |
| ashwagandha | 14.0x | Strong shift |
| chamomile | 5.9x | Smaller shift |
| creatine | 5.7x | Smaller shift |
| collagen | 4.9x | Smaller shift |
| third party | 3.3x | Smaller shift |

All nine words are composition, ingredient, or specification terms. None are
brand-feeling words. Ratios are normalized word-frequency counts (search-on
divided by search-off), so a word that simply appears more often because
search-on responses run longer does not get undue credit.

## Why it matters

This lines up with the model's own confidence pattern from the browsing
study: the noise floor (how often the model changes its own answer with
nothing else changed) sits at 47% with search off and drops to 27% with
search on. The model is not only naming different brands when it can read a
product page, it is also guessing less. Retrieval pulls facts. Memory pulls
a feeling. The words on a brand's own product page are not just for
shoppers; when the model can retrieve that page, its own language becomes
the language the model uses to describe the brand.

## Design

Same 50 prompts, run twice: once with web search available, once without.
Category held constant across both conditions. Word frequency counted in
each condition and normalized by total word volume, so response length
differences between conditions do not bias the ratio.

- Prompts: 50, identical in both conditions
- Conditions: search on vs. search off
- Held constant: category, prompt set
- Scoring: normalized word-frequency ratio
- Status: corroborated, not preliminary

## What is shown here

The nine words in `data.csv` are the largest ratio shifts found in this
analysis, not an exhaustive list of every word that moved. They are the
words with the clearest signal, not a claim that no other word changed.

## Package contents

- `data.csv` — word-frequency ratios, noise floor figures, and design parameters
- `methodology.md` — full method and limitations
- `Charts/word_frequency_shift_search_on_vs_off.png` — ranked bar chart of the nine words

## Citation

Atom Foundry. "Search Does Not Just Change Who AI Recommends. It Changes the
Words It Uses." Atom Foundry Research, July 2026.
https://atomfoundry.dev/research/search-changes-the-vocabulary

DOI: pending (to be assigned on publication to Zenodo)
