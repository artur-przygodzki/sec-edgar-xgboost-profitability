# 📈 SEC EDGAR Corporate Profitability Prediction with XGBoost & SHAP

## 📌 Project Overview
This project presents an end-to-end Machine Learning pipeline designed to evaluate financial health and predict company profitability based on financial ratios derived from **U.S. SEC EDGAR filings**.

By combining **XGBoost** classification with **Explainable AI (SHAP)**, the model provides both high predictive performance (**>85% accuracy**) and transparent, actionable insights for investment decision-making.

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
