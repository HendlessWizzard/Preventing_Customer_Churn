# 🧠 Customer Churn Prediction for RosTeleCom

📌 **Project Description**

RosTeleCom, a major telecommunications provider, faced increased customer churn. The goal of this project is to develop an automated machine learning model that can identify high-risk customers before they leave. This enables timely retention measures and reduces financial losses.

[You can see my notebook here](telecom_ml_pipline.ipynb)  

🎯 **Project Objectives:**

- Build a model to predict customer churn (binary classification).  
- Achieve **ROC AUC ≥ 0.90** for practical deployment.  
- Compare multiple algorithms (Logistic Regression, Random Forest, CatBoost).  
- Implement an end-to-end solution: from loading CSV files to saving the model for API integration.

🎯 **Key Tasks:**

- Load and review four tables (`contract_new.csv`, `personal_new.csv`, `internet_new.csv`, `phone_new.csv`).  
- Preprocess data: convert types (`datetime`, `float`), fill missing values, create the target variable.  
- Extract and encode features: tenure (`period`), demographics, internet/phone services, billing details.  
- Address class imbalance with SMOTE.  
- Train and compare models: Logistic Regression, Random Forest, CatBoost.  
- Tune hyperparameters via `RandomizedSearchCV` with `TimeSeriesSplit` (or `StratifiedKFold`).  
- Evaluate performance: metrics **ROC AUC**, Accuracy, Precision, Recall, F1-score.  
- Interpretability: analyze feature importance using SHAP.  
- Save the final model and preprocessor for deployment.

📂 **README Contents:**

- 📌 [Methods and Libraries Used](#methods-and-libraries-used)  
- 📚 **Libraries:**  
  - `pandas`, `numpy` — data manipulation  
  - `scikit-learn`, `imbalanced-learn` — ML and balancing  
  - `phik` — correlation analysis  
  - `catboost`, `lightgbm`, `xgboost` — ensemble models  
  - `matplotlib`, `seaborn` — visualization  
  - `shap` — model interpretation  
  - `joblib` — model serialization  
- 🤖 **Methods:**  
  - Preprocess and merge tables (outer join on `customerID`).  
  - Identify and handle missing values: `TotalCharges`, `EndDate = "No"`.  
  - Create target variable `churn` (1/0).  
  - One-Hot Encode categorical features.  
  - Scale numerical features with `StandardScaler`.  
  - Use SMOTE to balance classes.  
  - Train models:  
    - **Logistic Regression** (`class_weight='balanced'`)  
    - **Random Forest Classifier**  
    - **CatBoost Classifier** (no manual categorical encoding required)  
  - Hyperparameter tuning: `RandomizedSearchCV` + 3-fold CV optimizing `roc_auc`.  
  - Evaluate: ROC AUC, confusion matrix, Precision/Recall.  
  - SHAP analysis for interpretation.

---

## 📈 Key Results

🏆 **Best Model — CatBoost Classifier**  
- **CV ROC AUC:** 0.8880  
- **Test ROC AUC:** 0.9246  
- **Accuracy:** 0.82  
- **Precision:** 0.79  
- **Recall:** 0.75  
- **F1-score:** 0.77  

✅ The model meets the required performance and demonstrates excellent generalization.  
✅ SHAP analysis identified key churn drivers: tenure (`period`), contract type (`Type_Two year`), partner status (`Partner_Yes`), monthly charges (`MonthlyCharges`), payment method (`PaymentMethod`).  
✅ The model is ready for API integration to manage TeleDom’s customer base in real time.

---

## 🔧 Installation

1. **Clone the repository**  
   ```bash
   git clone https://github.com/
HendlessWizzard/telecom-churn-prediction.git
   cd telecom-churn-prediction
