# Methodology

This study follows the standard Atom Foundry Research Methodology.

For the complete research framework, see:

`/METHODOLOGY.md`

---

# Objective

Identify which measurable signal best predicts AI recommendation behavior across time.

---

# Research Question

Are recommendation outcomes primarily explained by external characteristics of brands, or by the model's own historical recommendation behavior?

---

# Experimental Design

The study compares multiple independent signals against recommendation frequency.

External signals include:

- Store quality
- Public fame
- Web traces
- Intent

An internal signal was created by comparing recommendation position across two independent collection periods.

June and July datasets were generated independently using identical buyer intents.

---

# Dataset

- AI Model: GPT-4o
- Brand-intent pairs: 1,082
- Time periods: June and July
- Buyer intents: 50 identical prompts

---

# Evaluation

Pearson correlation was used to evaluate predictive relationships between:

- Position → Position
- Frequency → Frequency
- Position → Frequency

Recommendation drift was evaluated separately across repeated scans spanning up to 15 days.

---

# Metrics

Primary metrics included:

- Pearson Correlation
- R²
- Recommendation Stability
- Recommendation Drift
- External Signal Correlation

---

# Validation

Robustness checks included:

- Separate collection periods
- Independent database tables
- Model update between collection periods
- Drift analysis over multiple time intervals

---

# Limitations

The study evaluates observable recommendation behavior.

Correlation measures predictive stability rather than causal mechanisms.

---

Published by Atom Foundry

AI Commerce Intelligence™
