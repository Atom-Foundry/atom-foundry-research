# Methodology — Structured Markup vs. Plain Prose (Study #38)

## Research question

Does structuring the same set of facts about a brand as a bulleted list,
instead of a flowing prose paragraph, change how much of that content a
language model cites or reuses when it later answers an open buyer
question about that brand's category?

## Design

- **Model:** gpt-4o throughout, single-turn.
- **Brands:** 4 (Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom),
  one brand injected per call, no competitor named anywhere in the design.
- **Facts injected:** exactly 3 per brand, always all 3 together — a
  concrete specific claim, a disclosed-synthetic third-party authority
  mention, and a familiarity claim. This is the same "full stack" content
  used as the AFSM condition in the prior Signal Hierarchy study.
- **Conditions (2):**
  - **Prose** — the 3 facts joined into a single paragraph.
  - **Structured** — the 3 facts presented as a 3-line bulleted list, one
    fact per line.
  Both conditions carry byte-for-byte identical factual content; only the
  separators between facts change.
- **Injection mechanism:** the facts are placed in the system message as
  "Additional context retrieved for this query: {brand_name}\n{blurb}",
  reused unchanged from the earlier Fact Injection and Hidden Context
  studies in this series.
- **User prompt:** an open buyer question with no brand name in it (e.g.
  "I'm looking for handmade ceramic dinner plates. What would you
  recommend and why?"), one real purchase intent drawn from each brand's
  own set of 20.
- **Sample:** 4 brands x 2 conditions x 20 purchase intents x 5 repeats x
  2 independent rounds = **1,600 total calls** (800 per round).
- **Rounds:** round 1 and round 2 were run from scratch on independent
  random seeds, not a re-run of the same calls, following this series'
  standard mandatory-replication convention.

## Outcome measures

1. **Citation rate.** For each of the 3 injected facts, an LLM judge
   (gpt-4o, temperature 0) was asked whether that specific fact was cited
   or clearly paraphrased in the model's response — one judge call per
   fact, **2,400 judge calls per round, 4,800 total**. Citation rate is
   the share of the 3 facts scored as cited, averaged per response.
2. **Vocabulary lift.** 5 distinctive terms per brand (certifications,
   proper nouns, specific phrases tied to the injected facts) were
   pre-registered before data collection. Vocabulary lift is the share of
   those 5 terms that appear verbatim (deterministic substring match, no
   judge call) in the model's response.

Two supporting measures were also logged for robustness checks: response
word count, and whether the brand was named at all in the response.

## Statistical method

Primary evidence is a **clustered paired t-test** comparing prose vs.
structured at the cluster level, where a cluster is one (brand x purchase
intent) combination, each cluster's value averaged over its 5 repeats.
This gives **80 independent clusters per round** (4 brands x 20 intents).
The test is run separately, from scratch, on each round's own data; no
scipy dependency, p-values from a normal-approximation on the t-statistic.

Under this series' no-file-drawer rule, an effect only counts as a
confirmed finding if it holds the same direction and the same statistical
significance in both independently-run rounds.

## Results summary

See `data.csv` for the full table. Both outcomes (citation rate,
vocabulary lift) showed structured format performing **below** prose in
both rounds, with p < 0.005 in three of the four round-level tests and
p < 0.0001 in one.

## Robustness checks

- **Response length.** Structured responses averaged 141.3 words combined
  across both rounds, vs. 145.1 for prose — not longer, if anything
  slightly shorter. This rules out "prose simply has more room to cite
  things" as the explanation for the citation-rate gap.
- **Brand-mention rate.** Both conditions sat at or above 99.8% in both
  rounds, essentially at ceiling. The citation-rate gap is not a byproduct
  of structured responses failing to name the brand at all.

## Limitations

- All injected facts are synthetic (disclosed-synthetic authority mention,
  synthetic familiarity claim), the same convention used throughout this
  research series, not scraped from real press or real market-recognition
  data.
- Only 4 brands were tested, the same category-coverage limitation
  acknowledged throughout this series.
- Single-turn, gpt-4o only; a single injection mechanism (system-message
  "retrieved context" framing), not tested against live web search or a
  model actually invoking a retrieval tool.
- The 5 vocabulary terms per brand are a judgment call about what counts
  as distinctive, fixed before data collection, not an exhaustive or
  algorithmically derived list.
- 5 repeats per cell follows this series' standard convention, not a
  power calculation specific to this study.

## Source

Full report, including the "why it matters" discussion and links to the
two prior format-signal studies in this series (Winner vs Loser, Signal
Hierarchy): https://atomfoundry.dev/research/structured-markup
