# Methodology -- Nothing About Your Brand Predicts Recommendation. The Model's Own Past Behavior Does.

Reproduced from the published study page. All figures are aggregate
results; no row-level raw data is included in this package.

## Part one: four external signals

Store quality, public fame, and how intent separates recommended stores
from stores that never get picked had each already been tested in earlier
studies in this series, landing at 0.7%, 1.2%, and 1.2% respectively (R-squared
against recommendation frequency). One layer was still untouched: web
traces, meaning how visible a brand is across the open web, not just its
own store.

Web traces were measured using distinct domains mentioning the brand,
whether the brand's own site turns up at all, and mentions on review
sites, comparing the most reliably recommended brands (a 301-brand core
that survives every model and search setting tested) against everything
else.

- Distinct domains, core: 8.1 vs. rest: 7.9
- Own site present, core: 58% vs. rest: 44%
- Review site mentions, core: 2.7
- Correlation to frequency: r = 0.046, R-squared = 0.2%

**Disclosed handicap:** the search API used for this measurement rejects
quoted phrase queries on its free tier, so every search ran unquoted, a
looser and noisier match than preferred. Both groups took the same
handicap, so the comparison between them still holds, but the absolute
counts should be read as approximate.

## Part two: the internal signal (month-to-month self-prediction)

- **Brand-intent pairs:** 1,082
- **Intents:** same 50, both periods
- **Periods compared:** June 2026 vs. July 2026
- **Method:** Pearson correlation on raw values
- **Circularity check:** June and July come from different collection
  runs, stored in different tables, spanning a change to the underlying
  model in between. If June still predicts July under those conditions,
  the thing being measured is more stable than the pipeline that measured
  it.

### Results

| Comparison | r | R-squared |
|---|---|---|
| Position -> Position | 0.784 | 61.4% |
| Frequency -> Frequency | 0.737 | 54.4% |
| Position -> Frequency | -0.565 | 31.9% |

The Position -> Frequency correlation is negative because a better
position number (lower is better) lines up with a higher frequency, which
is expected if position and frequency are two views of the same underlying
stability.

**Do not mix this with the 53.6% ceiling reported elsewhere in this
series:** that earlier number was a Spearman correlation. Spearman's
version of this same self-prediction test comes out at 91.3%, not 61.4%.
Pearson and Spearman answer related but different questions and should
never be reported as the same statistic.

## Companion finding: no drift after 15 days

Comparing the same sweep against itself produces about 44% turnover from
ordinary noise alone (unrelated to real change). This was extended out to
1 day, 14 days, and 15 days apart, on 234,283 scans across 57,242 domains.
On a full 0-100% scale, four measurements spread across 15 days sit on top
of one another, hugging the same noise floor as a sweep compared with
itself. The gap between the noise floor and every later measurement rounds
to zero.

## Supporting evidence (structural, not noisy)

- Top 3 brands' combined share of recommendations across 10 categories
  (coffee to food and snacks) ranges from 28.5 to 30.3, a 1.8-point range.
  The same concentration holds everywhere tested.
- Total score for the most stable "core" brands vs. everyone else
  recommended: 53.4 vs. 55.0. The core has worse stores, not better,
  echoing the same reversal found across the full population.

## Limitations (stated on the published page)

- The web-traces measurement used unquoted search queries due to a free-
  tier API restriction, making absolute counts approximate (though both
  compared groups took the same handicap).
- This is a correlational, not causal, design; June and July are compared,
  not manipulated.
- 301-brand "core" definition (reliably recommended across every model and
  search setting tested) is specific to this series' own data and may not
  generalize to a different collection methodology.
