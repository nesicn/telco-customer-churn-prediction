```
# IBM Telco Customer Churn Dataset

## Overview & Source

This folder documents the dataset used in the churn analysis. To maintain repository efficiency and ensure reproducibility, raw data is pulled dynamically from the official IBM repository during script execution.

* **Dataset Source:** [IBM Telco Customer Churn (ICP4D)](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)
* **Format:** CSV
* **Size:** 7,043 records, 21 columns

```
## Data Dictionary

| Feature | Data Type | Description |
| :--- | :--- | :--- |
| `customerID` | String | Unique ID assigned to each customer |
| `gender` | Categorical | Gender (`Male`, `Female`) |
| `SeniorCitizen` | Binary | Age indicator (`1` = 65+, `0` = Under 65) |
| `tenure` | Integer | Total duration of subscription in months |
| `Contract` | Categorical | Subscription term (`Month-to-month`, `One year`, `Two year`) |
| `MonthlyCharges` | Float | Current monthly subscription fee ($) |
| `TotalCharges` | Float | Cumulative subscription fee paid to date ($) |
| `InternetService` | Categorical | Connection type (`DSL`, `Fiber optic`, `No`) |
| `PaymentMethod` | Categorical | Billing method (`Electronic check`, `Mailed check`, `Bank transfer`, `Credit card`) |
| `TechSupport` | Categorical | Technical assistance subscription (`Yes`, `No`, `No internet service`) |
| **`Churn`** | **Target** | **Customer churn status (`Yes` = Terminated, `No` = Retained)** |

---

## Accessing the Data

To fetch the raw dataset programmatically in Python:

```python
import pandas as pd

url = "[https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv](https://raw.githubusercontent.com/IBM/telco-customer-churn-on-icp4d/master/data/Telco-Customer-Churn.csv)"
df = pd.read_csv(url)

```
