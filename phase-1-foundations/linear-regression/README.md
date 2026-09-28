# Linear Regression

This section of the Paper Replications project studies **Linear Regression** through three progressively more challenging empirical applications in financial engineering and climate economics.

The exercises progress from simple linear regression to multiple regression and finally to panel-data methods with fixed effects and interaction terms. The objective is to connect the statistical foundations of linear regression with research-style empirical applications.

## Problems

| Problem | Application | Main Concepts | Research Anchor |
|---|---|---|---|
| **Problem 1** | CAPM Beta Estimation for the U.S. Energy Industry | Simple linear regression, alpha, beta, residuals, R² | Fama & French (1993) |
| **Problem 2** | CAPM vs. Fama-French 3-Factor Model | Multiple linear regression, factor models, adjusted R², AIC/BIC | Fama & French (1993) |
| **Problem 3** | Temperature Shocks and Economic Growth | Panel data, fixed effects, interaction terms, clustered standard errors | Dell, Jones & Olken (2012) |

---

## Problem 1 — CAPM Beta Estimation

### Research Question

**What is the market beta of the U.S. Energy industry portfolio?**

I begin with a CAPM-style regression in which Energy industry excess returns are explained using market excess returns.

The exercise introduces:

- simple linear regression;
- intercept (alpha);
- slope coefficient (beta);
- statistical significance;
- R-squared; and
- residual analysis.

### Data

Monthly data are obtained from the **Kenneth R. French Data Library**, using:

- Fama/French 3 Factors; and
- 10 Industry Portfolios.

The Energy (`Enrgy`) portfolio is used as the industry portfolio.

### Main Result

The estimated market beta is **0.8878**, suggesting that the Energy portfolio moves positively with the market but with slightly lower market sensitivity.

The model produces an **R² of 0.539**, meaning that approximately 53.9% of the variation in Energy industry excess returns is explained by movements in the market excess return.

The estimated alpha is positive but statistically insignificant.

---

## Problem 2 — CAPM vs. Fama-French 3-Factor Model

### Research Question

**Does adding size and value factors improve the explanation of Energy industry excess returns compared with the single-factor CAPM?**

The second problem extends the first regression by introducing:

- Market excess return (`Mkt-RF`);
- Small Minus Big (`SMB`); and
- High Minus Low (`HML`).

This provides an introduction to **multiple linear regression** and empirical factor models.

### Model Comparison

| Model | R² | Adjusted R² |
|---|---:|---:|
| CAPM | 0.5393 | 0.5389 |
| Fama-French 3-Factor | 0.5748 | 0.5738 |

The Fama-French specification provides greater explanatory power than the single-factor CAPM in this exercise.

The market beta remains positive and statistically significant. The negative SMB coefficient suggests that the Energy portfolio behaves more like large-cap stocks, while the positive HML coefficient indicates value-stock characteristics.

---

## Problem 3 — Temperature Shocks and Economic Growth

### Research Question

**Do hotter years reduce economic growth, and is the effect stronger in poorer countries?**

The final Linear Regression problem moves from financial applications to **climate economics**.

The exercise is inspired by:

> Dell, Jones and Olken (2012), *Temperature Shocks and Economic Growth: Evidence from the Last Half Century*.

Rather than using a simple cross-sectional regression, this problem introduces:

- country-year panel data;
- country fixed effects;
- year fixed effects;
- interaction terms;
- clustered standard errors; and
- heterogeneous effects across income groups.

### Data

The exercise uses the `climate_panel.dta` dataset from the authors' public replication package.

### Main Result

The estimated coefficient on the interaction between **Temperature × Poor** is:

**−1.2095**

with a p-value of approximately **0.0008**.

The combined estimated temperature effect for poorer countries is approximately **−0.9667**.

In this specification, a 1°C increase in annual temperature is therefore associated with approximately a **0.97 percentage point reduction in GDP per capita growth for poorer countries**.

The corresponding temperature effect for richer countries is not statistically significant.

---

## What I Learned

Across the three problems, I progressively moved from a simple one-predictor regression to substantially richer empirical specifications.

The exercises helped me understand:

- how regression coefficients should be interpreted economically;
- the distinction between statistical and economic significance;
- residual analysis;
- simple versus multiple regression;
- factor-based asset-pricing models;
- model-fit measures such as R² and adjusted R²;
- panel data;
- fixed effects;
- interaction terms;
- clustered standard errors; and
- how regression methods can be applied across finance and climate economics.

An important part of the exercises was also identifying and correcting data-processing and modelling issues rather than treating the initial model output as automatically correct.

---

## Repository Contents

```text id="pr36av"
linear-regression/
│
├── README.md
│
├── notebooks/
│   ├── 01_linear_regression_easy.ipynb
│   ├── 02_linear_regression_ff3_energy.ipynb
│   └── 03_linear_regression_temperature_growth.ipynb
│
├── reports/
│   └── LinReg_Report.pdf
│
└── handwritten-notes/
    └── Linear Regression_Theory.pdf
```

The **notebooks** contain the empirical implementations, the **report** contains the detailed results and interpretations, and the **handwritten notes** document the theoretical and mathematical learning underlying the exercises.

---

## References

Fama, E.F. and French, K.R. (1993) 'Common risk factors in the returns on stocks and bonds', *Journal of Financial Economics*, 33(1), pp. 3–56.

Dell, M., Jones, B.F. and Olken, B.A. (2012) 'Temperature shocks and economic growth: Evidence from the last half century', *American Economic Journal: Macroeconomics*, 4(3), pp. 66–95.

French, K.R. — Kenneth R. French Data Library.

Dell, M., Jones, B.F. and Olken, B.A. — Replication data for *Temperature Shocks and Economic Growth: Evidence from the Last Half Century*.
