# Methodology

## Research question

Does category type moderate how much authority and brand familiarity signals move the recommended brand?

## Experimental design

The study uses the same broad category axis as the PDP Specificity study:

- 4 functional categories
- 4 trust and safety sensitive categories
- 8 real brands total
- 2 independent experimental rounds
- 20 purchase intents
- 5 repeats per condition
- 4 conditions per brand
- 3,200 calls per round
- 6,400 calls total, plus matched judge calls
- gpt-4o
- forced two-way brand choice
- no rating in the room

The four conditions cross signal type (authority or familiarity) with which brand possesses the added fact (target or competitor).

## Brands

### Functional

- Barbaro Mojo — Cuban-style hot sauce, vs. Gindo's
- Hearthloom — handmade ceramic dinnerware, vs. Kilnmere
- Bellroy — slim leather wallets, vs. Herschel
- Zigpoll — Shopify post-purchase survey tool, vs. SurveyMonkey

### Trust and safety sensitive

- Colored Organics — organic baby clothes, vs. Finn + Emma
- BodyArtForms — body piercing jewelry, vs. Painful Pleasures
- Wild One — dog gear, vs. Ruffwear
- Primally Pure — natural deodorant, vs. Native Deodorant

## Outcome

The primary descriptive measure is the **follow-the-signal rate**: the share of calls in which the model selected whichever brand received the added authority or familiarity sentence.

A flat 50% would indicate no observed movement attributable to the added sentence under this forced-choice setup.

The primary inferential test is the category type × signal level likelihood-ratio interaction, run separately for authority and familiarity in each independent round.

## Results

Authority:

- Functional: 65.4% in Round 1; 64.9% in Round 2.
- Trust/safety sensitive: 74.5% in Round 1; 74.0% in Round 2.
- Interaction LR: 461.93 in Round 1; 433.11 in Round 2.

Familiarity:

- Functional: 60.0% in Round 1; 60.4% in Round 2.
- Trust/safety sensitive: 74.4% in Round 1; 73.5% in Round 2.
- Interaction LR: 381.87 in Round 1; 380.2 in Round 2.

Both interaction effects replicated in the same direction.

## Bias check

Across both rounds combined, the target brand won 69.2% of the time when named first (n=1,595) and 67.5% when named second (n=1,605), a 1.7 percentage-point gap.

## Brand-level heterogeneity

The category average contains substantial variation between brands. Bellroy and Zigpoll were close to 50% for both signals in both rounds, while Hearthloom and Barbaro Mojo showed stronger effects. Among trust/safety brands, BodyArtForms was around 95–97%, Colored Organics around 81–85%, while Wild One and Primally Pure were lower, around 52–68%.

## Scope and limitations

This is a controlled behavioral experiment, not a claim about all AI systems or all ecommerce categories.

The study uses one model and a forced-choice setup. The sample contains eight brands, and category labels are necessarily simplified. The specificity comparison is between this study and the separate PDP Specificity study rather than a single unified experiment over the same eight brands.

The absence of ratings is intentional. The study therefore isolates authority and familiarity rather than measuring their interaction with a rating signal.
