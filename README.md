# ML Paper Replications

A structured, learn-by-doing repository for studying machine learning through paper-inspired empirical problems in **financial engineering, economics, and climate risk**.

The objective of this project is not simply to implement machine learning algorithms, but to understand the **theory, mathematics, empirical methodology, model behaviour, and interpretation** behind them.

Each model is studied through a combination of:

- theoretical and mathematical study;
- handwritten notes;
- Jupyter Notebook implementations;
- paper-inspired empirical problems;
- model evaluation and visualisation; and
- written reports interpreting the empirical results.

---

## Project Structure

The project is divided into three phases of increasing complexity.

### Phase 1: Foundations

Phase 1 focuses on regression and regularisation methods that provide the statistical foundation for later machine-learning models.

| Model | Status |
|---|---|
| Linear Regression | ✅ Completed |
| Logistic Regression | ✅ Completed |
| Ridge Regression | ✅ Completed |
| LASSO Regression | ✅ Completed |
| Elastic Net | ✅ Completed |

---

### Phase 2: Classical Machine Learning

Phase 2 extends the project to classical supervised and unsupervised machine-learning methods.

Topics include models such as:

- Decision Trees
- Random Forests
- Gradient Boosting
- Support Vector Machines
- k-Nearest Neighbours
- Naive Bayes
- Principal Component Analysis (PCA)
- k-Means Clustering

Additional classical machine-learning methods are incorporated as the project progresses.

---

### Phase 3: Neural Networks

Phase 3 is reserved for neural networks and related methods.

Neural networks are treated as a separate phase because they introduce a substantially larger theoretical and computational framework than the classical machine-learning models covered in Phases 1 and 2.

---

## Repository Organisation

The repository is organised primarily by **phase → model → learning material**.

```text
ml-paper-replications/
│
├── README.md
│
├── phase-1-foundations/
│   ├── linear-regression/
│   │   ├── README.md
│   │   ├── notebooks/
│   │   ├── reports/
│   │   └── handwritten-notes/
│   │
│   ├── logistic-regression/
│   │   ├── README.md
│   │   ├── notebooks/
│   │   ├── reports/
│   │   └── handwritten-notes/
│   │
│   ├── ridge-regression/
│   ├── lasso-regression/
│   └── elastic-net/
│
├── phase-2-classical-ml/
│   └── ...
│
└── phase-3-neural-networks/
    └── ...
```

Only completed or actively developed sections are added to the repository as the project progresses.

---

## Learning Approach

For each machine-learning model, I follow a four-stage workflow:

**1. Theory and Mathematics**

I first study the statistical intuition and mathematical foundations of the model. Handwritten notes are included where appropriate to document this learning process.

**2. Empirical Implementation**

I implement the model in Python using Jupyter Notebooks. The emphasis is on understanding each stage of the modelling process rather than treating machine-learning libraries as black boxes.

**3. Paper-Inspired Problems**

Each model is applied to empirical problems motivated by academic research and real-world applications. The problems primarily draw from:

- Financial Engineering
- Financial Economics
- Macroeconomics
- Climate Economics
- Climate Risk

**4. Interpretation**

The final stage focuses on interpreting model outputs, diagnostics, figures, predictive performance, limitations, and economic or financial implications.

Detailed PDF reports accompany the computational work where appropriate.

---

## Current Phase

The project began with **Phase 1: Foundations**, covering:

`Linear Regression → Logistic Regression → Ridge → LASSO → Elastic Net`

The repository is progressively being expanded to include the completed Phase 2 models before moving to **Phase 3: Neural Networks**.

---

## Tools

The empirical exercises primarily use:

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- statsmodels
- Matplotlib

Other libraries are introduced where required by a particular problem.

---

## Purpose

This repository serves three related purposes:

1. to develop a rigorous understanding of machine-learning methods;
2. to connect statistical theory with empirical applications in finance, economics, and climate research; and
3. to maintain a reproducible record of my progression from theoretical understanding to independent empirical implementation.

The emphasis throughout the project is therefore on **understanding, implementation, interpretation, and reproducibility**, rather than simply achieving the highest predictive performance.

---

## Author

**Abhishek Kumar Singh**  
MSc Financial Engineering  
University of Glasgow
