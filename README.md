# Climate-Aware Equity Risk Classification 
### Question: Can climate-related corporate disclosures help identify periods of elevated market risk? 
This project explores that question using **NLP-derived climate signals, Fama-French factors & Maching learning**.

## Project Overview 
Corporate climate disclosures contain a large amount of unstructured information- but does that information provide useful signals about market risk? 

This project builds an end-to-end pipeline that combines:

- SEC 10-K climate-related text signals
- Firm-level climate measures
- Fama–French market factors
- Momentum
- Machine learning classification
- Explainable AI using SHAP

The goal was to classify **high-risk vs lower-risk market periods** and test whether climate information adds predictive value beyond traditional market factors.

## Data Pipeline 
The analysis combines large-scale firm-level & market datasets across multiple stages:
`Raw Climate Data` → `Cleaning & SQL Analysis` → `Feature Engineering` → `Market Aggregation` → `ML Classification` → `SHAP & Ablation Analysis`

The underlying datasets contain **100K+ firm-year observations** and **400K+ firm-quarter observations** before cleaning and transformation.

## Models
4 approaches were evaluated :
- Baseline classifier
- L1 Logistic Regression
- Random Forest
- XGBoost

Time-aware train/validation/test splits were used to reduce look-ahead bias.

## Results

On the held-out **2022–2024 test period (35 months)**:

| Model | Macro F1 | Accuracy |
|---|---:|---:|
| Logistic Regression | 0.340 | 51.4% |
| Random Forest | 0.385 | 45.7% |
| **XGBoost** | **0.524** | **54.3%** |

**XGBoost produced the strongest classification performance**, correctly identifying a subset of high-risk months while maintaining a relatively controlled number of false alarms.

The project also produced an important negative result: overall ranking performance remained weak on the small out-of-sample test set, suggesting that climate disclosure signals should **not be treated as standalone market-timing predictors**.

That limitation became part of the analysis rather than something to hide.

## Explainability

SHAP analysis was used to understand what drove model predictions.

Traditional market variables — including **risk-free rate, momentum, and SMB** — remained dominant, while climate-related variables contributed less but non-zero explanatory power.

An ablation framework was also used to test whether climate features added incremental predictive value beyond conventional market factors.

## Tech Stack

`Python` · `Pandas` · `NumPy` · `SQL` · `SQLite` · `Scikit-learn` · `XGBoost` · `SHAP` · `NLP` · `VADER` · `FinBERT` · `LDA` · `Matplotlib` · `Seaborn`

## Repository Structure

```text
climate-risk-ml/
│
├── notebooks/
│   └── climate_risk_classification.ipynb
│
├── data/
├── results/
├── src/
├── .gitignore
└── README.md
