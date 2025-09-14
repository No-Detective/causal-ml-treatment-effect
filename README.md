# Causal ML Treatment Effect

This project implements an end-to-end **causal inference pipeline** to estimate the true effect of a treatment (e.g., product exposure, marketing campaign) on user conversions.  
It combines state-of-the-art methods from statistics and machine learning with clear diagnostics and business impact translation.

---

## 📌 Features
- **Propensity Score Modeling**
  - Logistic regression to estimate treatment probabilities
  - Common support checks and trimming
- **Treatment Effect Estimation**
  - Inverse Probability of Treatment Weighting (IPTW) with stabilized weights
  - Augmented Inverse Probability Weighting (AIPW, doubly robust)
  - Propensity score matching for ATT (with optional caliper/k-NN)
  - Instrumental Variables (IV) for Local Average Treatment Effect (LATE), when exposure ≠ assignment
- **Heterogeneous Effects**
  - Conditional Average Treatment Effects (CATE) via T-learner
  - Uplift curve analysis for targeted policies
- **Diagnostics**
  - Balance checks (standardized mean differences)
  - Propensity overlap plots
  - Weight distribution plots
- **Business Readout**
  - Translates ATE into **incremental conversions and revenue impact**
