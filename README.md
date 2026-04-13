Corporate Credit Risk Scorecard & Explainable AI (XAI)
Project Overview
This project develops a B2B Credit Scoring model to predict bankruptcy risk. It simulates a consulting approach integrating traditional financial statement indicators with synthetic behavioral data regarding commercial payments.
Business Context
In credit management, financial statements alone (historical data) often lack the reactivity needed for real-time risk assessment. This project demonstrates how integrating "Alternative Data"—such as payment delays and unpaid invoices—creates more robust and predictive scorecards for modern risk management.
Dataset & Feature Engineering
•	Source: Company Bankruptcy Prediction (Taiwan Economic Journal).
•	Financial Features: Balance sheet ratios including Net Value Per Share, Debt Ratio, and Cash Flow.
•	Behavioral Features (The "CRIBIS Touch"): I engineered two synthetic variables to simulate credit bureau data:
o	Days_Past_Due: Average days of payment delay beyond the due date.
o	Unpaid_Invoices_Ratio: Percentage of invoices remaining unpaid in the current period.
Methodology
1.	Data Quality & Preprocessing: Handled column sanitization, missing values, and feature scaling via StandardScaler.
2.	Imbalance Management: Addressed the rare nature of bankruptcy events (target imbalance) using the class_weight='balanced' parameter.
3.	Modeling: Implemented Logistic Regression for its high interpretability—a critical requirement for banking and regulatory rating models (Basel III/IV compliance).
Key Results
The model achieved excellent performance, proving the high discriminatory power of behavioral data:
•	AUC-ROC Score: 0.94
•	Recall (Class 1): 0.86 (Strong capability to capture actual defaults).

Explainable AI (SHAP)
To ensure transparency and "Right to Explanation" (GDPR/AI Act compliance), I utilized SHAP (SHapley Additive exPlanations) to interpret model drivers.
Note: Add your SHAP plot image here to visualize feature importance.
The analysis confirms that:
•	Net Value Per Share is the primary financial safeguard.
•	Payment Delays (Days_Past_Due) act as an immediate leading indicator of financial distress.
Tech Stack
•	Language: Python
•	Libraries: Pandas, NumPy, Scikit-learn, SHAP, Seaborn.
•	Environment: VS Code / Jupyter Notebooks.
