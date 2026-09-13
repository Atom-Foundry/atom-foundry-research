# Methodology

## Study metadata

- **Study:** The Model Had Real Web Search. It Never Once Reached for It.
- **Study number:** #28
- **Published:** September 11, 2026
- **Model:** gpt-4o
- **API:** OpenAI Responses API
- **Tool:** `web_search_preview`
- **Primary unit:** brand × buyer-question prompt × repeat
- **Brands:** 4, reused from Fact Injection
- **Buyer prompts:** 20 per brand
- **Main repeats:** 10 per prompt
- **Main live-search calls:** 800
- **Confirmatory rerun:** 160 calls, 2 repeats per prompt
- **Total real API calls:** 960
- **Diagnostic:** 3 prompts
- **Brand detection:** deterministic substring matching, no LLM judge

## Research design

The purpose was to test the step between **possession** and **deployment** measured in Fact Injection.

Fact Injection manually placed a real, verified brand fact into the system message and measured the resulting mention-rate lift. That represents a simulated successful retrieval.

Live Retrieval removed the hand-placed fact and instead enabled OpenAI's live web-search tool.

The same brands, facts, and buyer-question prompts were reused so that the comparison isolates the mechanism by which information reaches context as closely as possible.

## Conditions

### Published baseline

The no-search, no-injection baseline from the earlier report data. The model answers from its existing knowledge.

### Live-search condition

The same buyer questions were submitted through the Responses API with `web_search_preview` available. Nothing was manually injected.

### Fact Injection ceiling

Previously published injected results. The verified fact was placed directly into the system message. These values are reused unchanged and are not new observations in this study.

## Main measurements

### Search-tool invocation rate

The proportion of real API calls that produced a web-search tool invocation.

Main result:

**0 / 960 = 0%**

The 960 total includes the 800-call main run and 160-call confirmatory rerun.

### Live-search mention rate

The proportion of calls in which the tracked brand was detected in the model response.

Reported live-search rates:

- Brand A: 0.5% (1 / 200)
- Brand B: 2.5% (5 / 200)
- Brand C: 13.5% (27 / 200)
- Brand D: 0% (0 / 200)

### Realized ceiling

The study defines realized ceiling as:

`(live rate - baseline) / (injected rate - baseline)`

The published study reports:

- Brand A: -0.8%
- Brand B: -3.6%
- Brand C: -3.8%
- Brand D: 0%

These are not interpreted as meaningful negative retrieval effects. They describe where the live-search condition landed relative to the baseline and the theoretical injected ceiling.

### Fact usage among live mentions

Among the 33 cells where a tracked brand was mentioned, 12 used the specific fact:

**12 / 33 = 36.4%**

This is reported only for completeness. The study explicitly states that the sample is too thin to support a meaningful standalone fact-usage finding.

## Diagnostic

A three-prompt diagnostic was run to test whether the zero invocation result reflected a broken search tool.

The same model, tool, and API structure were used. Two prompts were rephrased to be explicitly time-sensitive.

Result:

**2 / 3 diagnostic prompts invoked search**, and each successful call returned ten real citations.

This supports interpreting the main zero as a tool-choice result for the tested prompt style rather than a technical failure of the search tool.

## Statistical treatment

The main finding is a direct tool-invocation count rather than a comparison requiring an effect-size estimate.

The live-search mention rates are reported as observed aggregate proportions. The underlying study used the same deterministic detection approach throughout and did not use an LLM judge for winner detection.

## Data boundaries

No row-level observations are reconstructed in this repository from the published aggregate report.

The CSV contains only metrics explicitly reported in the source HTML.

The baseline and Fact Injection ceiling are reused reference values from prior studies, not newly collected observations in this study.

## Limitations

1. **Prompt scope:** The result is specific to the open buyer-question phrasing used across the series, such as “What's a good X for Y?”
2. **Model scope:** Only gpt-4o was tested.
3. **Technical mechanism:** Responses API + `web_search_preview` differs from the Chat Completions mechanism used elsewhere in the series.
4. **Brand cohort:** Four deliberately underperforming brands were selected as a floor-case cohort, not as a representative ecommerce sample.
5. **Time gap:** Baseline and injected-ceiling data are older than the live-search collection.
6. **Fact-usage sample:** Only 33 cells were eligible for fact-usage judging.
7. **Tool-choice inference:** The study establishes that search did not fire under the tested conditions; it does not identify the model's internal reason for that choice.

## Interpretation boundary

The strongest defensible statement is:

> With real web search enabled, gpt-4o invoked it 0 of 960 times for the tested open buyer-question prompts, while a small diagnostic using explicitly time-sensitive phrasing triggered search 2 of 3 times.

That is a statement about observed behavior under a defined prompt and API configuration, not a universal claim about model retrieval behavior.
