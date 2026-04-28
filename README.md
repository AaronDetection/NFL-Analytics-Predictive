# 🏈 NFL Analytics 2025 — Predictive Modeling & Feature Engineering

Predictive framework for offensive performance (Points Per Game) in the 2024-25 NFL season. Built in R with Boruta feature selection, OLS regression, and Support Vector Regression.

---

## What this project does

Builds and validates a model to estimate team PPG from offensive and preseason metrics — then stress-tests it by intentionally including a collinear variable (PD_2024) to show what breaks and why.

The goal wasn't just a working model. It was to understand which metrics actually drive scoring vs. which ones just correlate with it.

---

## Stack

- **Language:** R
- **Libraries:** Boruta, e1071 (SVR), Tidyverse, ggplot2, corrplot
- **Data:** XLS/CSV — Offensive, Defensive, and Preseason datasets merged via relational joins

---

## Modeling approach

| Model | Formula | Key insight |
|---|---|---|
| Baseline | PPG ~ MoV + OSRS + PD_2024 | PD and MoV are collinear (r=1.00) — coefficients flip sign |
| Optimized | PPG ~ MoV + OSRS + L_2024 | Coherent coefficients, OSRS as primary driver |
| SVR | Radial kernel | Captures non-linear variance in high-volatility teams |

Boruta confirmed OSRS and PF as top predictors. DSRS, SoS, and team name were correctly rejected as noise.

---

## Key results

- **OSRS is 40% more predictive** of scoring than defensive metrics in the current NFL meta
- Model parsimony held: removing PD improved stability without losing R-squared
- SVR with radial kernel outperformed OLS for teams with high game-to-game variance (pass-heavy offenses)

---

## Why this matters beyond football

The workflow — ETL from raw XLS, feature engineering, multicollinearity diagnosis, iterative model refinement — translates directly to any domain where you're predicting a continuous outcome from correlated business metrics. The NFL context makes it readable; the methodology is what's transferable.

---

## Files

```
├── data/
│   ├── offensive_stats_2024.csv
│   ├── defensive_stats_2024.csv
│   └── preseason_2024.csv
├── scripts/
│   ├── 01_etl_merge.R
│   ├── 02_boruta_selection.R
│   ├── 03_regression_models.R
│   └── 04_svr_analysis.R
└── plots/
    ├── boruta_importance.png
    ├── correlation_heatmap.png
    └── predicted_vs_actual.png
```
