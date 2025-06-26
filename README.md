# PaisaBazaar_fraudAnalysis

End-to-end pipeline that turns anonymised customer-credit CSVs into a
production-ready scoring engine.

---

## 1 · Why It Matters
Classic rule-based scorecards miss subtle borrower behaviour.
This project builds a data-driven model that

* keeps **~92 %** of the information while throwing out half the columns
  (PCA → 14 comps), and
* bumps accuracy from **0.64 → 0.75**, cutting the costliest errors in half.

---

## 2 · Pipeline Overview

| Stage                    | Key Actions & Tools                          |
|--------------------------|----------------------------------------------|
| Profiling & Cleanup      | `pandas`, duplicates, missing radar          |
| Feature Engineering      | 4 custom ratios + type fixes                 |
| Visual Storytelling      | 10 + plots (`matplotlib`, `seaborn`)         |
| Class Re-balancing       | SMOTE (`imblearn`)                           |
| Dimensionality Cut-down  | PCA → 14 PCs, ~92 % variance (`sklearn`)     |
| Modelling                | Random Forest (benchmark) → XGBoost (final)  |
| Evaluation               | Accuracy + two 3×3 confusion matrices        |

---

## 3 · Results 🚀

| Model          | Accuracy | Good → Poor | Standard → Poor |
|----------------|---------:|------------:|----------------:|
| Random Forest  | 12 808 / 20 000 = **0.64** | **715** | **2 507** |
| **XGBoost**    | 14 913 / 20 000 = **0.75** | **267** | **1 490** |

*Mis-rating our safest borrowers (‘Good’ → ‘Poor’) dropped **63 %**;
standard customers downgraded to ‘Poor’ fell **40 %**.*

---


