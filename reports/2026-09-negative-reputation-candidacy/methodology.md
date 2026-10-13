# Methodology — A Bad Rating Barely Touches Candidacy. It Wrecks the Final Round. (Study #42)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 1.0
- **Brands:** 4, reused from Winner vs Loser
- **Conditions:** neutral vs. negative reputation
- **Probe A, candidacy:** open buyer question, brand_mentioned string match
- **Probe B, selection:** forced two-way vs. named competitor, LLM judge
- **Total calls:** 1,600 chat (800 per probe), 800 judge on Probe B

## Pre-registration and data

Pre-registered before the run. The design, the two probes, and which of them would support versus contradict the pre-filtering theory were written into STUDY-DESIGN.md before the run, so this page reports the pre-registered comparison, not one picked after seeing the data.

## Results table

| Brand | Candidacy, neutral → negative | Selection, neutral → negative |
|---|---|---|
| Barbaro Mojo | 23.0% → 62.0% | 97.0% → 30.0% |
| BodyArtForms | 26.0% → 16.0% | 100.0% → 56.0% |
| Colored Organics | 80.0% → 86.0% | 41.0% → 0.0% |
| Hearthloom | 27.0% → 54.0% | 96.0% → 11.0% |

## Findings and interpretation (from the study page)

### A specific claim from a comment thread, tested instead of argued

Jairo Guerrero, commenting on a post about mentions as a KPI, argued that AI filters out bad actors before a mention ever happens, so negative mentions are rare in the wild and a mention itself is a good enough proxy for success. Our own candidacy-vs-selection framework already complicates that story in general (599 stores ever recommended against 60,325 that never were, and the factors that predict getting in barely predict winning once you're in), but we had never tested negative reputation specifically as its own variable. Every earlier study in this cluster, Winner vs Loser, Authority Signal, Brand Familiarity, Signal Hierarchy, pit positive signals against each other or against a neutral rating. None of them asked whether a bad reputation blocks a brand from being mentioned at all, or only costs it the final pick.


### Two probes, same brands, same negative signal

4 brands were reused byte-identical from Winner vs Loser: Colored Organics, BodyArtForms, Barbaro Mojo, Hearthloom, each with its existing competitor and 20 real buyer intents. A new disclosed-synthetic negative reputation was added for each brand, a low star rating, a review count, and one short, generic, non-safety complaint (shipping delays, slow customer service, a confusing checkout), deliberately avoiding product-safety or quality claims given two of the four brands sit in trust-sensitive categories (baby clothes, body piercing jewelry).


### Candidacy barely moves. Selection collapses

Across all 4 brands (cluster mean, neutral minus negative), candidacy rate did not fall under negative reputation, it rose, from 39.0% to 54.5% (for 3 of the 4 brands individually, see below). The forced-selection win rate, in a direct head-to-head against a named competitor, collapsed from 83.5% to 24.3%, a 59.2 point swing. Negative reputation does not appear to block a brand from being mentioned in an open buyer question. It decides the outcome once that brand is put in direct competition.


### The selection collapse holds for every brand. Candidacy is messier

Selection rate falls for all 4 brands without exception, sharply for 3 of them. Candidacy moves in the opposite direction for 3 of 4 brands, and falls for only one, BodyArtForms.


### Not pre-filtering. A finals problem

Jairo Guerrero's theory was that bad actors get filtered out before a mention ever happens, which would show up here as candidacy falling under negative reputation. It did not fall, on average it rose. What actually happens is that negative reputation is close to fatal once a brand is put in direct comparison with a named competitor, win rate falling from 83.5% to 24.3%. A brand carrying a bad reputation is not being quietly removed from consideration. It is still showing up in the room. It is just losing, decisively, every time it has to stand next to someone else.


## Limitations

- Same small cohort as Winner vs Loser, not a new or broader sample. Extending to more brands is an open follow-up.
- The negative rating and complaint were written by one researcher, disclosed as synthetic, deliberately generic and non-safety to avoid realistic negative claims about a real company.
- Probe A and Probe B use different prompts and mechanisms. The comparison between them is descriptive, not a formal statistical interaction in one model.
- gpt-4o only, single round. Self-grading risk on Probe B is mitigated by reusing the already-validated Winner vs Loser judge prompt unchanged.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *A Bad Rating Barely Touches Candidacy. It Wrecks the Final Round.* Recommendation Intelligence Research™, Study #42. https://atomfoundry.dev/research/negative-reputation-candidacy. https://doi.org/10.5281/zenodo.23350436
