# Logistic Regression

This section of the Paper Replications project studies **Logistic Regression** through applications in credit risk, macroeconomic recession prediction, and financial-market direction forecasting.

The problems progress from a standard binary classification problem to threshold tuning, cost-sensitive classification, rare-event prediction, and finally a more difficult financial forecasting application.

The objective is not only to understand how Logistic Regression produces binary predictions, but also to understand how a classification model should be evaluated when different types of prediction errors have different economic consequences.

---

## Problems

| Problem | Application | Main Concepts | Research Anchor |
|---|---|---|---|
| **Problem 5** | German Credit Risk Classification | Binary classification, probabilities, confusion matrix, precision, recall, F1-score, ROC-AUC | Beninel, Bouaguel & Belmufti (2012) |
| **Problem 5A** | Threshold Tuning and Cost-Sensitive Credit Risk | Classification thresholds, false negatives, asymmetric costs, cost-sensitive evaluation | Beninel, Bouaguel & Belmufti (2012); Shen et al. (2019) |
| **Problem 6** | U.S. Recession Prediction Using the Yield Curve | Rare-event classification, yield curve, recession probability, ROC-AUC | Estrella & Mishkin (1996) |
| **Problem 6A** | Threshold Tuning for Recession Prediction | Rare events, threshold tuning, recall, false alarms, misclassification costs | Estrella & Mishkin (1996) |
| **Problem 7** | Forecasting Monthly Stock-Market Direction | Financial classification, lagged predictors, benchmark comparison, predictive limitations | Nyberg (2011) |

---

## Problem 5 — Credit Risk Classification Using German Credit Data

### Research Question

**Can borrower characteristics be used to predict whether a borrower represents a good or bad credit risk?**

This problem introduces Logistic Regression as the first classification model in the project.

The target variable is converted into:

- `0` = Good credit risk
- `1` = Bad credit risk

The exercise introduces:

- predicted probabilities;
- binary classification;
- classification thresholds;
- confusion matrices;
- precision and recall;
- F1-score;
- ROC curves; and
- ROC-AUC.

### Data

The exercise uses the **Statlog German Credit Data** from the UCI Machine Learning Repository.

### Main Results

The Logistic Regression model achieved:

- **Accuracy: 0.7700**
- **ROC-AUC: approximately 0.796**

The results show that the model has useful ability to distinguish between good-risk and bad-risk borrowers.

However, the exercise also demonstrates why accuracy alone is insufficient in credit-risk modelling. In particular, incorrectly classifying a genuinely bad borrower as good can be considerably more consequential than some other classification errors.

This motivates the threshold-tuning exercise in Problem 5A.

---

## Problem 5A — Threshold Tuning and Cost-Sensitive Credit Risk

Problem 5A extends the German Credit model by asking:

**Can we reduce the number of bad borrowers incorrectly classified as good by changing the classification threshold?**

Instead of assuming that every classification error has the same consequence, I use the following illustrative cost structure:

- False positive cost = **1**
- False negative cost = **5**

At the default threshold of **0.50**, the model produced:

- 44 false negatives;
- bad-risk recall of 0.5111;
- accuracy of 0.7700; and
- total cost of 245.

After threshold tuning, a threshold of **0.20** produced:

- 14 false negatives;
- bad-risk recall of 0.8444;
- accuracy of 0.6733; and
- total cost of 154.

The exercise demonstrates that the threshold producing the highest accuracy is not necessarily the most useful threshold when classification errors have asymmetric economic costs.

---

## Problem 6 — Predicting U.S. Recession Probability Using the Yield Curve

### Research Question

**Can the Treasury yield spread help predict whether the U.S. economy will experience a recession within the next 12 months?**

This exercise is motivated by the literature examining the yield curve as a leading indicator of economic activity.

The predictor is:

**10-Year Treasury Yield − 3-Month Treasury Yield**

The binary target is:

- `0` = No recession within the next 12 months
- `1` = Recession within the next 12 months

### Data

The exercise uses two FRED series:

- `T10Y3MM` — 10-Year Treasury Constant Maturity Minus 3-Month Treasury Constant Maturity;
- `USREC` — NBER-based U.S. recession indicator.

### Main Results

The estimated coefficient on the yield spread is:

**−1.0731**

The negative coefficient is consistent with the economic idea that a lower or inverted yield spread is associated with a higher predicted probability of recession.

The model achieved:

- **Accuracy: 0.7383**
- **ROC-AUC: 0.5596**
- **Recession recall: approximately 0.26**

Although overall accuracy appears relatively high, the model performs much better at identifying non-recession observations than recession-risk observations.

This provides an important example of why accuracy can be misleading when the event being predicted is relatively rare.

---

## Problem 6A — Threshold Tuning for Recession Prediction

Problem 6A investigates whether lowering the default classification threshold improves recession detection.

At the default threshold of **0.50**, recession recall was only:

**0.2619**

After lowering the threshold to **0.35**, recession recall increased to:

**0.5476**

False negatives fell from **31 to 19**, although false positives increased from **36 to 67**.

Using the same illustrative asymmetric cost structure:

- False positive cost = **1**
- False negative cost = **5**

total misclassification cost decreased from:

**191 → 162**

The exercise demonstrates that rare-event classification involves an explicit trade-off between missing important events and generating additional false alarms.

---

## Problem 7 — Forecasting Monthly Stock-Market Direction

### Research Question

**Can lagged market information and macro-financial variables help predict whether the next month's U.S. market excess return will be positive?**

The target variable is:

- `1` = Next month's market excess return is positive
- `0` = Next month's market excess return is zero or negative

The predictors include lagged information from:

- market excess returns;
- SMB;
- HML;
- the Treasury yield spread;
- the recession indicator; and
- rolling 12-month market volatility.

### Data

The exercise combines:

- Kenneth R. French Data Library — Fama/French 3 Factors;
- FRED `T10Y3MM`; and
- FRED `USREC`.

### Main Results

The Logistic Regression model achieved:

- **Accuracy: 0.6070**
- **ROC-AUC: 0.5213**

However, a naive strategy that always predicted a positive market month would have achieved approximately:

**0.642 accuracy**

The Logistic Regression model therefore did not outperform this simple benchmark.

The confusion matrix also revealed an important weakness: the model correctly identified **zero non-positive months** at the default 0.50 threshold.

This exercise provides an important negative result. Successfully implementing a statistically valid model does not imply that the model possesses useful predictive power.

---

## What I Learned

Across these problems, I moved from basic binary classification to increasingly realistic questions about how classification models should be evaluated and used.

The exercises helped me understand:

- how Logistic Regression converts a linear predictor into a probability;
- binary classification and classification thresholds;
- confusion matrices;
- precision, recall and F1-score;
- ROC curves and ROC-AUC;
- why accuracy can be misleading;
- class imbalance and rare-event prediction;
- false positives and false negatives;
- threshold tuning;
- asymmetric misclassification costs;
- cost-sensitive model evaluation;
- benchmark comparisons; and
- why technically correct models can still have weak out-of-sample predictive performance.

A particularly important lesson from these exercises is that model evaluation must depend on the **economic purpose of the prediction problem**, rather than relying on a single statistical metric.

---

## Repository Contents

```text
logistic-regression/
│
├── README.md
│
├── notebooks/
│   ├── 05_logistic_regression_credit_risk.ipynb
│   ├── 05A_logistic_regression_threshold_tuning_credit_risk.ipynb
│   ├── 06_logistic_regression_recession_yield_curve.ipynb
│   └── 07_logistic_regression_stock_market_direction.ipynb
│
├── reports/
│   └── LogReg_Report.pdf
│
└── handwritten-notes/
    └── Logistic Regression_Theory.pdf
