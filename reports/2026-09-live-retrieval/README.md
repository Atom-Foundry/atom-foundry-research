# The Model Had Real Web Search. It Never Once Reached for It.

**Atom Foundry — Recommendation Intelligence Research™ · Study #28**

> We gave gpt-4o real web search and asked it the same open buyer questions behind Fact Injection. Across 960 real API calls, it invoked the search tool zero times.

## Research question

When live web search is actually available, will the model retrieve a brand fact on its own during an ordinary open buyer question?

This study bridges the simulated retrieval ceiling measured in **Fact Injection** with a real tool-enabled setting. The same four deliberately underperforming brands, the same verified facts, and the same 20 buyer-question prompts per brand were reused. The only new variable was how the fact could enter context: through real `web_search_preview`, with nothing hand-placed.

## Headline results

| Result | Finding |
|---|---:|
| Real calls that invoked search | **0 / 960** |
| Confirmatory rerun | **0 / 160** |
| Diagnostic prompts that invoked search | **2 / 3** |
| Live-search mention rate, Brand A | **0.5%** |
| Live-search mention rate, Brand B | **2.5%** |
| Live-search mention rate, Brand C | **13.5%** |
| Live-search mention rate, Brand D | **0%** |
| Fact Injection average lift, for reference | **77.9 pp** |

## The experiment

### Same cohort, same prompts

The study reused four brands from Fact Injection, the same 20 already-published buyer-question prompts for each brand, and gpt-4o.

The main collection used:

- 4 brands
- 20 buyer prompts per brand
- 10 repeats per prompt
- 800 live-search calls
- 160-call confirmatory rerun
- 960 real API calls total
- OpenAI Responses API
- `web_search_preview` enabled
- deterministic brand detection
- no LLM judge for winner detection

The control and injected-ceiling numbers are reused unchanged from earlier studies rather than recollected.

## Finding 1: available is not the same as used

Across all 800 main-run calls and the separate 160-call confirmatory rerun, the model never invoked web search.

That does **not** show that the search tool was broken.

A three-prompt diagnostic used the same model, tool, and API structure but changed the phrasing to explicitly time-sensitive requests. Two of those three prompts triggered search, with ten real citations returned each time.

The result is therefore scoped to **tool choice for the open buyer-question prompt style**, not tool availability.

## Finding 2: mention rate barely moved

With search never firing, the live-search condition was functionally a memory-only condition for these calls.

| Brand | Published baseline | Live search | Fact Injection ceiling |
|---|---:|---:|---:|
| Brand A | 1.25% | **0.5%** | 97.5% |
| Brand B | 5.75% | **2.5%** | 97.0% |
| Brand C | 16.5% | **13.5%** | 96.0% |
| Brand D | 0% | **0%** | 44.5% |

The live-search condition did not approach the injected ceiling. Three of four brands moved slightly downward from baseline, consistent with ordinary sampling variation rather than a search effect.

## Finding 3: the gap is retrieval choice

Fact Injection showed what happens when a verified fact is successfully placed into context: average mention-rate lift was **77.9 percentage points**.

This study asks what happens when the model has to decide whether to retrieve that fact itself.

For the exact open buyer-question style used here, it did not.

That creates a useful distinction:

**Fact available to the system ≠ fact retrieved ≠ fact deployed in the recommendation.**

This study measures the middle step directly: whether live search is invoked.

## Fact usage among live mentions

There were 33 live-search cells in which a tracked brand was mentioned. Because search was never invoked and returned zero citations, any fact that appeared in those responses came from memory rather than live retrieval.

12 of the 33 cells used the specific fact, or **36.4%**.

The study explicitly treats this as a completeness metric, not as a reliable standalone fact-usage finding because the eligible sample is too small.

## What this means

The important result is not that web search is ineffective.

It is that **switching a search tool on does not guarantee that the model will use it**.

For ordinary open buyer questions, gpt-4o repeatedly answered without reaching for search. When the prompt was explicitly time-sensitive, the same tool worked.

So there are at least two separate layers:

1. **Tool availability** — search exists and can return grounded results.
2. **Tool choice** — the model decides whether the current question warrants search.

A brand cannot assume the second follows automatically from the first.

## What this does not prove

- It does not show that gpt-4o never searches.
- It does not generalize beyond the exact open buyer-question phrasing tested.
- It does not show that other models or API configurations make the same tool-choice decision.
- It does not provide a representative sample of ecommerce brands.
- It does not establish a reliable fact-usage rate from the 33 eligible live mentions.
- It does not contradict the separate finding that recommendations can change substantially once search actually happens; that result describes the post-search state, while this study measures whether search fires in the first place.

## Reproducibility

The experiment used the OpenAI Responses API with `web_search_preview`, logged tool invocations, and reused the published Fact Injection cohort and prompts.

The main run contained 800 calls followed by a separate 160-call confirmatory rerun. A three-prompt diagnostic was used to test whether the zero-invocation result could be explained by a broken tool.

Brand detection used deterministic substring matching rather than an LLM judge.

## Files

- `README.md` — study overview, results, interpretation, and limitations
- `methodology.md` — experimental design, definitions, and statistical notes
- `experiment-summary.csv` — aggregate metrics using the standard Atom Foundry schema
- `Charts/README.md` — chart descriptions and provenance
- `Charts/search-invocation-rate.svg`
- `Charts/live-search-mention-rate.svg`
- `Charts/realized-ceiling.svg`
- `Charts/baseline-live-injected.svg`

## Source

Published study: https://atomfoundry.dev/research/live-retrieval
