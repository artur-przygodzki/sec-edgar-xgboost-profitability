# 📈 SEC EDGAR Corporate Profitability Prediction with XGBoost & SHAP

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![XGBoost](https://img.shields.io/badge/Model-XGBoost-green.svg)](https://xgboost.readthedocs.io/)
[![XAI-SHAP](https://img.shields.io/badge/Explainability-SHAP-red.svg)](https://shap.readthedocs.io/)

## 📌 Project Overview
This project presents an end-to-end Machine Learning pipeline designed to evaluate financial health and predict company profitability based on financial ratios derived from **U.S. SEC EDGAR filings**.

By combining **XGBoost** classification with **Explainable AI (SHAP)**, the model provides both high predictive performance (**>85% accuracy**) and transparent, actionable insights for investment decision-making.

> 🔗 **Quick Access:** You can view the full code, execution outputs, and visualizations directly in GitHub by opening [operating_results_forecast.ipynb](operating_results_forecast.ipynb).

---

## 🔑 Key Financial & Modeling Insights

1. **Core Driver (ROA):** **Return on Assets (ROA)** emerged as the single most decisive factor driving profitability predictions.
2. **Data Leakage Prevention:** The `Operating Margin` ratio was explicitly excluded from the final classification model. While valuable during Initial Exploratory Data Analysis (EDA) for detecting operational anomalies, retaining it in the predictive phase causes **data leakage** (since operating income directly forms net income).
3. **Removal of ROE:** `Return on Equity (ROE)` was omitted due to mathematical instability caused by distressed companies with negative equity (generating misleading positive ratios) and redundancy with leverage metrics.
4. **Working Capital Efficiency:** The analysis confirmed that companies optimizing working capital and maintaining balanced liquidity perform significantly better than those burdened with excessive idle cash.

---

## 📊 Dataset & Feature Engineering

The model evaluates **9 fundamental financial metrics** across profitability, liquidity, leverage, and efficiency:

| Feature | Financial Category | Description |
| :--- | :--- | :--- |
| **`ROA`** | Profitability | Return on Assets ($\frac{\text{Net Income}}{\text{Total Assets}}$) |
| **`net_margin`** | Profitability | Net Profit Margin ($\frac{\text{Net Income}}{\text{Revenue}}$) |
| **`current_ratio`** | Liquidity | Current Assets / Current Liabilities |
| **`cash_ratio`** | Liquidity | Cash & Equivalents / Current Liabilities |
| **`working_capital_to_assets`** | Efficiency & Liquidity | Working Capital / Total Assets |
| **`debt_ratio`** | Solvency | Total Debt / Total Assets |
| **`debt_to_equity`** | Solvency | Total Debt / Shareholder's Equity |
| **`asset_turnover`** | Efficiency | Revenue / Total Assets |

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python 3.8+
* **Modeling:** XGBoost, Scikit-learn
* **Explainability (XAI):** SHAP (TreeExplainer)
* **Data Processing & Visualization:** Pandas, NumPy, Matplotlib, Seaborn
* **Environment:** Google Colab / Jupyter Notebook

---

* ## 💾 Dataset & Directory Structure

Due to GitHub repository size limitations, the complete SEC EDGAR quarterly dataset archive is hosted on Google Drive.

* **Dataset Download Link:** [SEC EDGAR Quarterly Datasets (Google Drive)](https://drive.google.com/file/d/1c96AZD95B6HBCUgKO63TfbVFIE0qw-yL/view?usp=sharing)

### Setup Data Instructions:
1. Download the zip archive from the link above.
2. Extract the contents directly into the project's root folder.
3. Ensure the folder layout matches the structure below before running the notebook.

```text
sec-edgar-xgboost-profitability/
├── 1Q2025/                         # SEC quarterly financial reports Q1 2025
├── 1Q2026/                         # SEC quarterly financial reports Q1 2026
├── 2Q2025/                         # SEC quarterly financial reports Q2 2025
├── 3Q2025/                         # SEC quarterly financial reports Q3 2025
├── 4Q2025/                         # SEC quarterly financial reports Q4 2025
├── operating_results_forecast.ipynb # Main analysis & modeling notebook
├── requirements.txt                # Python environment dependencies
└── README.md                       # Project documentation
