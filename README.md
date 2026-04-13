# Corporate Credit Risk Scorecard & Explainable AI (XAI)

## Project Overview
This project develops a **B2B Credit Scoring model** to predict bankruptcy risk.  
It simulates a consulting approach by integrating traditional financial statement indicators with synthetic behavioral data related to commercial payments.

## Business Context
In credit management, financial statements alone (historical data) often lack the reactivity needed for real-time risk assessment.  
This project demonstrates how integrating **Alternative Data** — such as payment delays and unpaid invoices — creates more robust and predictive scorecards for modern risk management.

## Dataset & Feature Engineering

**Source:** Company Bankruptcy Prediction (Taiwan Economic Journal)

### Financial Features
Balance sheet ratios including:
- Net Value Per Share
- Debt Ratio
- Cash Flow

### Behavioral Features ("CRIBIS Touch")
Two synthetic variables were engineered to simulate credit bureau data:
- **Days_Past_Due**: Average days of payment delay beyond the due date
- **Unpaid_Invoices_Ratio**: Percentage of invoices remaining unpaid in the current period

## Methodology

### 1. Data Quality & Preprocessing
- Column sanitization
- Missing value handling
- Feature scaling via `StandardScaler`

### 2. Imbalance Management
The rare nature of bankruptcy events was handled using:
- `class_weight='balanced'`

### 3. Modeling
Implemented **Logistic Regression** for its high interpretability, a critical requirement for banking and regulatory rating models (**Basel III/IV compliance**).

## Key Results
The model achieved excellent performance, confirming the high discriminatory power of behavioral data:

- **AUC-ROC Score:** 0.94
- **Recall (Class 1):** 0.86

This indicates a strong capability to capture actual defaults.

## Explainable AI (SHAP)
To ensure transparency and support the **Right to Explanation** under **GDPR / AI Act** compliance, SHAP (**SHapley Additive exPlanations**) was used to interpret model drivers.

> Add your SHAP plot image here to visualize feature importance.

The analysis confirms that:
- **Net Value Per Share** is the primary financial safeguard
- **Payment Delays (Days_Past_Due)** act as an immediate leading indicator of financial distress

## Tech Stack
- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, SHAP, Seaborn
- **Environment:** VS Code / Jupyter Notebooks
