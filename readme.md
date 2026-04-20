# 📊 Customer Churn Prediction

## 📌 Problem Statement
Customer churn is a critical challenge for businesses, as losing customers directly impacts revenue. The goal of this project is to build a machine learning model that can predict whether a customer is likely to churn, enabling proactive retention strategies.

---

## 📂 Dataset
- Total Customers: 7043  
- Churned Customers: 1869  
- Retained Customers: 5174  

The dataset is moderately imbalanced, which reflects real-world business scenarios.

---

## ⚙️ Project Workflow

### 1. Data Cleaning
- Converted `TotalCharges` from string to numeric
- Handled missing values using median imputation
- Removed irrelevant feature (`customerID`)

### 2. Exploratory Data Analysis (EDA)
Key insights:
- Customers with **low tenure** are more likely to churn  
- **High monthly charges** correlate with higher churn  
- Customers on **month-to-month contracts** show higher churn  
- Lack of services (security, tech support) increases churn  

---

### 3. Feature Engineering
- `TotalServices`: Total number of subscribed services  
- `IsMonthlyContract`: Flag for short-term contract customers  

These features capture **customer engagement and commitment**.

---

### 4. Feature Encoding
- Binary features → Label Encoding  
- Nominal features → One-Hot Encoding  
- Ordinal feature (`Contract`) → Label Encoding  

---

### 5. Feature Scaling
- Applied `StandardScaler` on numerical features:
  - Tenure  
  - MonthlyCharges  
  - TotalCharges  

---

## 🤖 Models Used

- Logistic Regression  
- Random Forest  
- XGBoost  

---

## 📊 Model Evaluation

Evaluation metrics:
- Accuracy  
- Precision  
- Recall (Primary focus)  
- F1 Score  
- ROC-AUC  

### Key Observations:
- Logistic Regression achieved **high recall**
- Random Forest had **low recall**, making it less suitable
- XGBoost provided a **better balance between precision and recall**

---

## 🔁 Cross Validation
- 5-fold cross-validation was performed
- Logistic Regression showed consistent recall performance

---

## ⚙️ Hyperparameter Tuning

- Logistic Regression: No significant improvement (default optimal)
- XGBoost: Improved performance after tuning

👉 XGBoost outperformed Logistic Regression after tuning

---

## 🎯 Threshold Tuning

- Applied to both Logistic Regression and XGBoost  
- Evaluated thresholds: 0.3, 0.4, 0.5, 0.6  

### Insight:
- Lower thresholds → Higher recall, lower precision  
- Higher thresholds → Higher precision, lower recall  

👉 Final Selection:
- **Model:** XGBoost  
- **Threshold:** 0.5  

This provides the best balance between:
- Identifying churn customers (recall)  
- Controlling false positives (precision)

---

## 📌 Feature Importance

Top drivers of churn:
- Contract type  
- Internet service (Fiber optic)  
- Payment method (Electronic check)  
- Lack of additional services  

---

## 💡 Business Insights

- Customers on **month-to-month contracts** are more likely to churn  
- Customers with **fiber optic internet** show higher churn  
- Customers paying via **electronic check** have higher churn risk  
- Customers using **fewer services** are less engaged and more likely to leave  

### Recommendations:
- Offer incentives for long-term contracts  
- Provide bundled services to increase engagement  
- Target high-risk customers with personalized retention offers  

---

## ⚠️ Limitations

- Model prioritizes recall, which may increase false positives  
- Further improvement can be achieved using pipelines and deployment strategies  

---

## 🚀 Future Improvements

- Implement full preprocessing pipeline  
- Deploy model using Flask/FastAPI  
- Add real-time prediction system  

---

## 🧠 Conclusion

XGBoost was selected as the final model after hyperparameter and threshold tuning, as it provides the best trade-off between recall and precision. The model effectively identifies high-risk churn customers, enabling data-driven retention strategies.

---

## 🛠️ Tech Stack

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- XGBoost  

---

## 📬 Author

Neha Yadav
