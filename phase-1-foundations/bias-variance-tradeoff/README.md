# Bias–Variance Trade-off

This section studies the **Bias–Variance Trade-off**, one of the central ideas in statistical learning and machine learning.

Rather than treating the bias–variance trade-off as a separate predictive model, I study it as a framework for understanding how **model complexity affects generalisation**. The empirical exercise uses polynomial regression of increasing degrees to examine the transition from underfitting to overfitting.

---

## Problem 4: Predicting Energy Industry Returns with Increasing Model Complexity

### Research Question

**How does increasing model complexity affect in-sample fit and out-of-sample predictive performance?**

The exercise investigates the bias–variance trade-off by progressively increasing the complexity of a regression model.

The target variable is the **Energy industry excess return**, while the **market excess return** is used as the predictor.

Polynomial regression models of increasing degrees are estimated and compared using their training and test performance.

### Research Anchor

The theoretical motivation is based on:

> Geman, Bienenstock and Doursat (1992), *Neural Networks and the Bias/Variance Dilemma*.

The paper provides a foundational discussion of the relationship between model complexity, bias, variance, and generalisation.

---

## Data

The empirical exercise uses monthly financial data from the **Kenneth R. French Data Library**, specifically:

- Fama/French 3 Factors; and
- 10 Industry Portfolios.

The Energy industry portfolio is used as the target portfolio.

---

## Methodology

I estimate polynomial regression models with increasing degrees of complexity.

For each model, I compare:

- training RMSE;
- test RMSE; and
- the gap between training and test performance.

This allows me to observe how increasing flexibility affects the model's ability to fit the training data and generalise to unseen observations.

The exercise therefore provides an empirical illustration of:

- underfitting;
- overfitting;
- model complexity;
- training versus test error;
- bias;
- variance; and
- out-of-sample generalisation.

---

## Main Results

The lowest test RMSE is obtained with the **degree-7 polynomial model**, with a test RMSE of approximately:

**5.8400**

However, the improvement relative to the simple **degree-1 model**, which has a test RMSE of approximately **5.8508**, is extremely small.

At higher polynomial degrees, particularly degrees 9 and 10, test performance deteriorates substantially despite the greater flexibility of the models.

This demonstrates an important principle: **greater model complexity does not necessarily translate into better out-of-sample prediction**.

The exercise also highlights numerical instability associated with high-degree polynomial terms, reinforcing the importance of careful preprocessing and model specification when using highly flexible models.

---

## What I Learned

This problem helped me understand that evaluating a machine-learning model requires more than examining how well it fits the training data.

In particular, I learned:

- why training error generally decreases as model complexity increases;
- why lower training error does not guarantee better prediction;
- how test error can be used to assess generalisation;
- the distinction between underfitting and overfitting;
- the conceptual roles of bias and variance;
- why an optimal level of model complexity may lie between extremely simple and extremely flexible models; and
- why simpler models can remain preferable when additional complexity produces negligible improvements in predictive performance.

The exercise also showed me how the bias–variance trade-off appears in an empirical financial application rather than only as a theoretical concept.

---

## Repository Contents

```text
bias-variance-tradeoff/
│
├── README.md
│
├── notebooks/
│   └── problem-04-bias-variance-tradeoff.ipynb
│
├── reports/
│   └── bias-variance-tradeoff-report.pdf
│
└── handwritten-notes/
    └── bias-variance-tradeoff-handwritten-notes.pdf
