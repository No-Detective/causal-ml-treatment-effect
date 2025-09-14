# 📈 Causal ML Treatment Effect Estimator

This project implements an end-to-end **causal inference pipeline** to measure the true effect of a treatment (e.g., product exposure, marketing campaign) on user conversions. It combines statistical estimators with machine learning models and translates results into measurable business impact.

---

## 🔧 **Features**

- **Propensity Score Estimation**  
  - Logistic regression to compute treatment probabilities  
  - Common support checks and trimming  

- **Treatment Effect Estimators**  
  - **IPTW** (Inverse Probability of Treatment Weighting) with stabilized weights  
  - **AIPW** (Augmented IPTW, doubly robust)  
  - **Propensity Score Matching** for ATT (with optional caliper / k-NN)  
  - **Instrumental Variables (IV)** for Local Average Treatment Effect (LATE)  

- **Diagnostics**  
  - Standardized Mean Differences (SMD) before vs after weighting  
  - Propensity overlap plots  
  - Weight stability checks  

- **Heterogeneous Effects**  
  - Conditional Average Treatment Effects (CATE) with T-learner  
  - Uplift curves for policy targeting  

- **Business Readout**  
  - Translates ATE into incremental conversions and revenue  

---

## 📌 **Technologies Used**

- Python  
- Jupyter Notebook  
- **pandas**, **numpy**  
- **scikit-learn**  
- **statsmodels**  
- **matplotlib**  

---

## 📈 **Methodology**

- **Propensity Score Modeling**  
  Logistic regression on pre-treatment features (`f0..f11`), with trimming to ensure overlap  

- **IPTW Estimation**  
  Weighted regression of outcome on treatment, robust SEs with heteroskedasticity-consistent errors  

- **AIPW Estimation**  
  Random forest outcome models for treated vs control, combined with doubly robust residuals  

- **Matching (ATT)**  
  Nearest-neighbor matching on propensity scores, with optional caliper to discard poor matches  

- **Uplift Modeling**  
  T-learner to estimate individual treatment effects and uplift curve for targeted rollout  

- **Business Impact**  
  Converts ATE into expected incremental conversions and revenue  
  - *Example*: ATE = **+0.09 pp** → ~**467 extra conversions** per 500k users (~**$4.7k** at $10 per conversion)  

---

## 🧠 **Learning Goals**

- Understand how causal inference adjusts for confounding  
- Practice implementing IPTW, AIPW, and matching from scratch  
- Learn to check **balance** and **overlap** to validate assumptions  
- Translate statistical effects into **clear business value**  

---

## 🧮 **Future Enhancements**

- Cross-fitting for AIPW to reduce bias  
- Probability calibration for random forest models  
- Advanced CATE models (X-learner, R-learner)  
- Interactive dashboard for decision makers

---

## 📂 Dataset
This project uses the [Uplift Modeling , Marketing Campaign Dataset](https://www.kaggle.com/datasets/arashnic/uplift-modeling)  
(14M samples, ~340 MB zipped).  
Due to size, the dataset is not included in this repository. Please download it manually and place it in the `data/` folder.
