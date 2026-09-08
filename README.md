# Telco Customer Churn Prediction (XGBoost)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1TuWTE-XI9oE4gUc6199-_XMo_-qJc-0H?usp=sharing#scrollTo=cb1c34ad)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)

An end-to-end Machine Learning and Business Intelligence solution designed to identify customer churn risks for a telecommunications provider using the IBM Telco dataset.

---

## 📌 Executive Summary

Customer churn directly impacts revenue in subscription-based services. This project builds a predictive pipeline using **XGBoost** to identify churn-prone customers prior to account termination, enabling proactive retention strategies.

* **Dataset Source:** [IBM Telco Customer Churn Dataset](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)
* **Dataset Size:** 7,043 customer records with 21 initial attributes.
* **Core Goal:** Predict `Churn` status (`0 = Retained`, `1 = Churned`) and provide strategic business insights.

---

## 📊 Feature Engineering & Pipeline

To improve predictive accuracy, custom features were engineered from raw transaction metrics:

1. **`AvgMonthlySpend`**: `TotalCharges / max(tenure, 1)` to evaluate spending velocity.
2. **`IsNewCustomer`**: Binary flag (`tenure < 6` months) targeting early-stage customer volatility.
3. **`HighSpender`**: Binary flag (`MonthlyCharges > median`) indicating high-tier pricing groups.
4. **Categorical Encoding**: Label encoding applied to `Contract`, `PaymentMethod`, `InternetService`, and `TechSupport`.

---

## ⚙️ Model Performance

The model was evaluated on a stratified 20% test split (`random_state=42`).

| Metric | Score | Business Interpretation |
| :--- | :--- | :--- |
| **Accuracy** | **81%** | Successfully classifies 4 out of 5 customer outcomes. |
| **ROC-AUC** | **0.837** | Strong discrimination power between churners and non-churners. |
| **Recall (Churn Class)** | **53%** | Captures over half of actual churners before termination. |

---

## 💡 Key Business Drivers & Recommendations

Analysis of feature importance reveals critical operational insights:

1. **Contract Type (Primary Factor ~49% Importance):** Month-to-month subscribers represent the overwhelming majority of churn risks. 
   * *Action:* Launch incentive-based campaigns to transition high-risk monthly subscribers to 1-year or 2-year contracts.
2. **Early-Tenure Volatility (First 6 Months):** New customers exhibit the highest attrition rate.
   * *Action:* Implement a dedicated 180-day onboarding experience to strengthen brand retention.
3. **Fiber Optic Service Concerns:** Fiber users exhibit higher churn compared to DSL, signaling potential technical service stability or pricing dissatisfaction.
   * *Action:* Conduct service quality reviews for Fiber Optic lines and provide proactive technical support outreach.

---

## 📁 Repository Structure

```text
├── data/
│   └── README.md                  # Dataset reference and links
├── notebooks/
│   └── telco_churn_analysis.ipynb # Colab notebook
├── .gitignore
├── README.md
└── requirements.txt
```
#🛠️ Quickstart Guide
Clone the Repository:

```
git clone [https://github.com/nesicn/telco-customer-churn-prediction.git](https://github.com/nesicn/telco-customer-churn-prediction.git)
cd telco-customer-churn-prediction
```
Install Dependencies:

```
pip install -r requirements.txt
```
Run Notebook / Script:

Open ```notebooks/telco_churn_analysis.ipynb``` in Visual Studio Code or Google Colab.
