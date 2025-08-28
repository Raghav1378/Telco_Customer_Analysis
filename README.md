# Telco Customer Churn & Revenue Prediction

**Author:** Raghav Ramani  
**LinkedIn:** [Raghav Ramani](https://www.linkedin.com/in/raghav-ramani-711b56256/)  
**Kaggle:** [RaghavRamani3232](https://www.kaggle.com/raghavramani3232)  
**X (Twitter):** [RamaniRagh763](https://x.com/RamaniRagh763)

---

## Project Overview
This project predicts **customer churn** and estimates **total charges** for a telecom company using machine learning.  
Goals:
- Identify customers likely to churn (binary classification)  
- Predict total charges (regression)  
- Provide actionable insights to reduce churn and maximize revenue

---

## Dataset
**Telco Customer Churn dataset** (`WA_Fn-UseC_-Telco-Customer-Churn.csv`) contains customer info including demographics, account details, subscription types, and payment methods.

**Key Features:**
- `gender`, `SeniorCitizen`, `Partner`, `Dependents`  
- `tenure`, `PhoneService`, `MultipleLines`  
- `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`  
- `Contract`, `PaperlessBilling`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`  
- **Target:** `Churn` (for classification)

---

## Methodology

### Data Preprocessing
- Handled missing values and converted `TotalCharges` to numeric  
- Created features: `tenure_group`, `CumulativeChurn`, `NumServices`  
- Standardized numeric features: `TotalCharges`, `NumServices`, `tenure`, `CumulativeChurn`  
- One-hot encoded categorical variables

### Exploratory Data Analysis (EDA)
- Distribution analysis of categorical features (`Contract`, `PaymentMethod`, `Churn`)  
- Correlation heatmaps for numeric and categorical features  
- Insights:
  - Higher monthly charges → higher churn probability  
  - Month-to-month contracts → higher churn rates  
  - Tenure < 12 months → higher churn likelihood  
  - Senior citizens and customers with multiple services → higher total charges

---

## Machine Learning Models

### Classification (Churn Prediction)
**Models Used:** Logistic Regression, Decision Tree, Random Forest, KNN, SVC, Bagging, AdaBoost, Gradient Boosting, XGBoost  
**Metrics:** Accuracy, Precision, Recall, F1 Score, ROC-AUC  
**Top Model:** **AdaBoost Classifier** – best balance across Recall, F1 Score, and ROC-AUC  
- Logistic Regression had slightly higher Accuracy & Precision  
- Example: Prediction for a random customer using AdaBoost, Logistic Regression, and Random Forest  

### Regression (Total Charges Prediction)
**Models Used:** Linear, Ridge, Lasso, Decision Tree, Random Forest, Gradient Boosting, Bagging, Voting, Stacking, KNN, SVR, XGBoost  
**Metrics:** RMSE, MAE, R² Score  
**Top Model:** **XGBoost Regressor**  
- Test RMSE: 0.0453  
- Test R²: 0.9979  
- Stable predictions across 5-fold cross-validation

---

## Key Insights
**Churn Analysis:**  
- High monthly charges and month-to-month contracts are strongest churn indicators  
- Customers using electronic checks → higher churn likelihood  
- Senior citizens → higher total charges  

**Revenue Analysis:**  
- Total charges influenced by tenure, subscription type, and service usage  
- Predictive models assist in forecasting customer billing  

**Feature Importance:**  
- `MonthlyCharges`, `Contract`, `tenure_group`, `NumServices` → key for churn  
- `Tenure`, `NumServices`, `CumulativeChurn` → key for total charge prediction

---

## Conclusion
- Provides a complete end-to-end ML pipeline for telecom churn and revenue prediction  
- **AdaBoost** recommended for churn prediction (balanced metrics)  
- **XGBoost** most accurate for total charges prediction (minimal error)  
- Business implications: target high-risk customers, plan retention strategies, anticipate revenue trends
