# We Invented a Brand With Zero History. Reviews Got It Picked Anyway

Recommendation Intelligence Research™ · Atom Foundry · August 2026

---

# Research Summary

Every prior study measured brands the model already knew. This study removes that memory footprint by inventing a brand and testing what evidence can get it chosen against entrenched category leaders.

---

# Research Question

What does it take for a brand with zero memory to get picked at all?

---

# Experimental Setup

- Model: gpt-4o
- Temperature: 0.7
- 50 open prompts, 10 runs each
- 36 entrenched category leaders selected by top brand winning ≥7/10
- 360 paired runs with zero evidence
- 1,080 evidence-injection runs
- 1,940 total model calls
- 10 invented brand names across categories

---

# Key Findings

- The invented brand won 0/360 runs with zero evidence.
- With an injected review score it won 53.1% of runs (p<0.0001).
- Press mentions produced 1.9% wins (p=0.241).
- Sales-volume claims produced 0.3% wins (p=1.000).
- At a stricter ≥8/10 incumbent threshold, reviews still won 47.8%, press 0.7%, volume 0.0%.

---

# Why It Matters

The cold-start result suggests that a brand with no learned footprint is effectively shut out absent evidence. A review signal can open the gate; generic press and sales-volume claims did not in this controlled test.

---

# Dataset

- 36 entrenched category leaders
- 1 invented brand per category
- 360 zero-evidence runs
- 1,080 evidence-injection runs
- 1,940 total model calls

---

# Methodology

Phase 1 identified entrenched leaders from 50 open intents, requiring the top brand to win at least 7 of 10 runs. Phase 2 paired each leader with an invented brand that had no training-data footprint and supplied no evidence. Phase 3 repeated the same pair while injecting one evidence type at a time: review score, press mention, or sales-volume claim. The invented names were created for the study and were not checked against a trademark database. A stricter ≥8/10 robustness cut was also tested.

For the study-specific implementation details see:

`methodology.md`

---

# Related Research

- Hand It a Rating, and It Follows Every Single Time
- The Fame Study
- We Widened the Fame Signal Four Ways. It Barely Moved
- How AI Decides

---

# Resources

- `Charts/evidence-win-rate.svg`
- `Charts/evidence-vs-floor.svg`
- `experiment-summary.csv`
- `methodology.md`

---

# Conclusion

The cold-start result suggests that a brand with no learned footprint is effectively shut out absent evidence. A review signal can open the gate; generic press and sales-volume claims did not in this controlled test.

Full write-up: https://atomfoundry.dev/research/cold-start

---

Published by **Atom Foundry**

Advancing AI Commerce Intelligence™ through open research.
