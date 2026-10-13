# Methodology — Describe a Company by Its Side Feature and It Falls Off the AI Shortlist: 82.8% to 24.0%. The Model Still Names Its Category Correctly. (Study #49)

Reproduced from the published study page. All figures are aggregate results; no row-level raw data is included in this package.

## Design

- **Model:** gpt-4o, temperature 0.7
- **Categories:** 20 invented B2B software categories, one target each
- **Task:** Name 3 of 12 companies for a buyer query, using only the descriptions shown
- **Round 1 (pilot):** 10 categories, 800 runs
- **Round 2 (main):** 20 categories, 1,200 runs, rivals written as richly as the target
- **Round 3 (follow-up):** 1,800 runs separating weight from order
- **Classification:** 1,800 forced-choice calls, six options, no judge
- **Statistics:** cluster bootstrap over categories, permutation tests, Bonferroni

## Pre-registration and data

Pre-registration. Hypotheses were written before the main round. Rounds 2 and 3 were added after seeing the previous round, to remove weaknesses in it: round 1 had a nonrandom ceiling, round 2 changed weight and order together. The pilot was run with an LLM judge for classification; it was replaced by forced choice in round 2 because the judge was unreliable.

## Results table

| Target's description | On the shortlist | 95% CI (bootstrap over categories) |
|---|---|---|
| Main round (round 2) |
| Core first, mostly about the core | 82.8% | 70.3–93.2% |
| Side feature first, mostly about the side feature | 24.0% | 12.3–36.5% |
| Same, plus a “Primary category” sentence | 27.5% | 15.7–40.0% |
| Follow-up (round 3) |
| Core first, mostly about the core | 87.7% | 76.7–96.0% |
| Even split, core first | 61.0% | 43.7–77.7% |
| Side feature first, mostly about the core | 59.0% | 42.7–74.3% |
| Written like the rivals (baseline) | 50.0% | 36.3–63.3% |
| Core first, mostly about the side feature | 45.0% | 28.7–61.7% |
| Side feature first, mostly about the side feature | 27.7% | 14.7–41.0% |

## Findings and interpretation (from the study page)

### Brand Legibility found no effect. It had no competition.

Brand Legibility varied how clearly a brand's real facts were framed and found candidacy at or near 100% regardless. But the brand was described in the prompt and competed with nobody for a slot, so there was a ceiling. A practitioner in a LinkedIn exchange put the open question sharply: accuracy is not the problem, hierarchy is. If the description does not make clear which capability defines the company and which ones support it, AI may classify it by the supporting one and leave it off the shortlist.

So we built a setting with competition. The model sees twelve company descriptions and has to name three for a buyer's query. We wrote three hypotheses down before running: a description dominated by the side capability lowers shortlisting; stating the primary category repairs it; and the model's classification of the company predicts whether it is shortlisted. The first was right. The second was wrong. The third could not be tested, because classification never varied.


### Twelve companies, three shortlist slots

Each of 20 invented B2B software categories (project management, payroll, endpoint security, CRM, and others) has a target company with a core capability and a side capability. The target competes with eleven invented rivals described in the same style and length. The model gets a buyer's query for the core category and names three companies. The target's description is the only thing that changes. The facts are the same in every condition. Only their weight and order change.


### Core first and core-heavy: 82.8%. Side feature dominant: 24.0%

With the same facts, a description that leads with the core capability and spends most of its words on it put the target on the shortlist 82.8% of the time. A description that leads with the side capability and spends most of its words on it did so 24.0% of the time, a drop of 58.8 points (p = 0.0003 after correction). The drop appears in 17 of 20 categories.


### The model names the core category correctly. Every time

Asked separately which of six categories describes the target (its core, its side feature, or four unrelated ones), the model chose the core category in 100% of 1,200 calls in every condition, including the one where the side feature dominates the description. It never classified the company by the side feature. So the company was not shortlisted less because the model misread what it is. It was shortlisted less because the description spends its evidence on something else.

Stating the primary category in the description (“Primary category: payroll software. Expense reports are a supporting feature.”) did not repair it: 27.5% against 24.0% (difference not significant). The pilot had shown the same: 74% against 73%. A label is not evidence. The model counts the evidence it is given.


### Both matter. Weight matters more than order

The main round changed two things at once: most of the text was about the side feature, and the side feature came first. A follow-up crossed them. With the core first, moving most of the text to the side feature cost 42.7 points (87.7% to 45.0%). With most of the text about the core, putting the side feature first cost 28.7 points (87.7% to 59.0%). With most of the text about the side feature, putting the core first recovered 17.3 points (27.7% to 45.0%). An even split with the core first landed at 61.0%.


## Limitations

- In this setting the problem is not misclassification and the fix is not a clearer label. The model identified the category correctly and still shortlisted the company far less when most of its description was about a side capability. What helped was putting the core capability first and spending most of the text on it. For a company whose homepage, profiles and listings lead with a side feature, that is a measurable cost in shortlisting, in this controlled setting.
- This links to earlier findings. Brand Legibility found that clearer framing barely changes candidacy when a brand is described alone. Here, with competition for three slots, how the evidence is distributed changes it a great deal. Candidacy is decided by relative weight of evidence among the options, not by a description being clear in isolation.
- The descriptions are placed in the prompt. This measures how the model weighs the text it is given, not how real systems form a company's identity from its website, profiles and press.
- Invented firms with invented names, B2B software only. The target's name looked more like a real brand than the rivals' names, which raised every rate; only differences between conditions are interpretable.
- gpt-4o and a three-name shortlist chosen from twelve descriptions. Other models, longer lists and open-ended answers may behave differently.
- Six-option forced choice with the core category named in the text. It shows the model can identify the category when offered one, not that it would name it unprompted.
- Rounds 2 and 3 were added after seeing the previous round, to remove its weaknesses. The finding that a stated primary category does not help was observed in the pilot and again in round 2.

Part of the Atom Foundry Recommendation Intelligence Research™ series.

## Citation

Atom Foundry (2026). *Describe a Company by Its Side Feature and It Falls Off the AI Shortlist: 82.8% to 24.0%. The Model Still Names Its Category Correctly.* Recommendation Intelligence Research™, Study #49. https://atomfoundry.dev/research/classification-candidacy. https://doi.org/10.5281/zenodo.23351156
