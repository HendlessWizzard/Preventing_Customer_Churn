# 🏁 Customer Churn Prediction for TeleDom

## Overview
TeleDom, a leading telecommunications provider, faced high customer churn and sought to proactively identify at-risk subscribers. This project develops a machine learning pipeline—from data ingestion through model deployment—to predict customer churn with high accuracy, enabling targeted retention strategies and reducing revenue loss.

**Key Objective:**  
- Build a model to predict churn (binary) with **ROC AUC ≥ 0.90** and **Precision/Recall** balanced for practical use.

---

## Table of Contents
- [Dataset](#dataset)  
- [Installation](#installation)  
- [Project Structure](#project-structure)  
- [Data Preprocessing](#data-preprocessing)  
- [Feature Engineering](#feature-engineering)  
- [Modeling](#modeling)  
- [Evaluation](#evaluation)  
- [Results](#results)  
- [Deployment](#deployment)  
- [Contributing](#contributing)  
- [License](#license)  

---

## Dataset
The data consists of four CSV files (as of February 1, 2020):

1. **contract_new.csv**  
   - `customerID`: unique client ID  
   - `BeginDate`, `EndDate`: contract start/end dates (`EndDate = 'No'` means active)  
   - `Type`: payment type (month-to-month, one-year, two-year)  
   - `PaperlessBilling`: electronic vs. paper billing  
   - `PaymentMethod`: e.g., electronic check, mailed check, bank transfer, credit card  
   - `MonthlyCharges`: monthly expense (float)  
   - `TotalCharges`: total lifetime charges (float)

2. **personal_new.csv**  
   - `customerID`  
   - `gender`: Male/Female  
   - `SeniorCitizen`: 1 (yes) / 0 (no)  
   - `Partner`: Yes/No  
   - `Dependents`: Yes/No

3. **internet_new.csv**  
   - `customerID`  
   - `InternetService`: DSL, Fiber optic, No  
   - `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`: Yes/No (or `no_internet`)

4. **phone_new.csv**  
   - `customerID`  
   - `MultipleLines`: Yes/No (or `no_phone`)

**Target Variable:**  
- `churn` = 1 if `EndDate` ≠ “No”; else 0.

---

## Installation
1. **Clone the repository**  
   ```bash
   git clone https://github.com/<your-username>/telecom-churn-prediction.git
   cd telecom-churn-prediction
