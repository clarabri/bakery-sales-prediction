# 🥐 Bakery Sales Forecasting — Neural Network vs. Baseline

> Can machine learning predict daily bakery sales better than a simple trend line?  
> Spoiler: Yes — by ~48% on average. Results vary by category.

![Python](https://img.shields.io/badge/Python-3.12.1-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow%2FKeras-orange)
![MAPE](https://img.shields.io/badge/Best%20MAPE-17.45%25-green)

---

## Business Problem

Bakeries face a daily trade-off: produce too much → waste, too little → lost revenue.
This project forecasts daily sales across **6 product categories** over a 5-year horizon
to support inventory and staffing decisions.

---

## TL;DR

| Model | MAPE |
|---|---|
| Baseline (Linear Regression) | 33.74% |
| **Neural Network** | **17.45%** |
| Improvement | ~48% |

- Best category: **Rolls (10.2%)**
- Most challenging: **Seasonal Bread (53%)** due to sparse data.

---

## Results

![Forecast Results](results_preview.png)

| Product | MAPE | Notes |
|---|---|---|
| Rolls | 10.2% | Most predictable — stable demand pattern |
| Cake | 13.5% | Strong weekend signal |
| Croissant | 15.6% | — |
| Bread | 17.8% | — |
| Confectionery | 24.5% | High variance |
| Seasonal Bread | 53.1% | Limited training data |

---

## Methodology

1. **EDA** — Weekly seasonality, holiday effects, category-specific trends
2. **Baseline** — Linear Regression (MAPE: 33.74%)
3. **Neural Network** — Keras Sequential with BatchNormalization & Dropout (MAPE: 17.45%)
4. **Evaluation** — Holdout period Aug 2018 – Jul 2019

---

## Key Learnings

- Day-of-week features were the strongest predictors
- Seasonal Bread underperforms due to irregular production cycles
- Neural net outperforms linear regression without heavy feature engineering

---

## Tools Used

|---|---|
| Language | Python 3.12.1 |
| Modeling | TensorFlow / Keras, statsmodels |
| Data | pandas, numpy |
| Evaluation | scikit-learn |
| Visualization | matplotlib |

---

## Quick Start
```bash
pip install -r requirements.txt
jupyter notebook notebooks/3_Model/best_model_neural_net.ipynb
```
