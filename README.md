# 🏥 Hospital Readmission Prediction Using Machine Learning

![Python](https://img.shields.io/badge/Python-3.11-blue)
![CatBoost](https://img.shields.io/badge/CatBoost-ML-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-red)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview

Hospital readmissions within 30 days are a major concern for healthcare providers because they increase healthcare costs, reduce hospital efficiency, and may indicate gaps in patient care. Early identification of patients at high risk of readmission can help clinicians implement targeted interventions and improve patient outcomes.

This project develops a machine learning model to predict **30-day hospital readmission** for diabetic patients using the **UCI Diabetes 130-US Hospitals Dataset**. Multiple machine learning algorithms were evaluated, and **CatBoost** achieved the best overall performance.

---
## Final Results

| Metric | Value |
|---------|------:|
| Best Model | CatBoost |
| ROC-AUC | **0.694** |
| Accuracy | **74%** |
| Precision | **21%** |
| Recall | **49%** |
| F1 Score | **0.30** |
## 🎯 Objectives

- Predict whether a diabetic patient will be readmitted within **30 days**.
- Identify the most important factors contributing to hospital readmission.
- Compare the performance of multiple machine learning algorithms.
- Interpret model predictions using explainable AI techniques (SHAP).

---

## 📊 Dataset

**Dataset:** Diabetes 130-US Hospitals Dataset

- **Source:** UCI Machine Learning Repository
- **Total Patient Encounters:** 101,766
- **Original Features:** 50
- **Final Features Used:** 46

The dataset contains demographic information, admission details, diagnoses, laboratory procedures, medications, healthcare utilization history, and readmission outcomes for diabetic patients.

---

## 🛠 Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- CatBoost
- XGBoost
- SHAP
- Jupyter Notebook

---

## 🔄 Project Workflow

### 1. Data Loading

- Loaded the UCI Diabetes dataset.
- Inspected dataset structure, dimensions, and data types.

---

### 2. Exploratory Data Analysis (EDA)

Performed comprehensive exploratory analysis on:

- Age
- Gender
- Race
- Time in hospital
- Number of laboratory procedures
- Number of medications
- Number of diagnoses
- Previous inpatient visits
- Previous outpatient visits
- Previous emergency visits
- Readmission distribution

---

### 3. Data Preprocessing

The following preprocessing steps were performed:

- Replaced `"?"` values with missing values (`NaN`)
- Removed features with excessive missing values:
  - `weight`
  - `max_glu_serum`
  - `A1Cresult`
- Imputed remaining missing values
- Removed identifier columns:
  - `encounter_id`
  - `patient_nbr`
- Created a binary target variable:
  - **1 = Readmitted within 30 days**
  - **0 = Otherwise**

---

### 4. Machine Learning Models

The following models were developed and evaluated:

- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost
- **CatBoost (Best Performing Model)**

---

## 📈 Model Performance

| Model | ROC-AUC |
|--------|--------:|
| Logistic Regression | 0.644 |
| Decision Tree | 0.668 |
| Random Forest | 0.657 |
| XGBoost | 0.589 |
| **CatBoost** | **0.694** |

### Final CatBoost Performance

| Metric | Score |
|---------|------:|
| Accuracy | 74% |
| Precision | 21% |
| Recall | 49% |
| F1-Score | 0.30 |
| ROC-AUC | **0.694** |

---

## 📌 Feature Importance

The CatBoost model identified the following variables as the strongest predictors of hospital readmission:

1. Discharge disposition
2. Previous inpatient admissions
3. Primary diagnosis
4. Number of laboratory procedures
5. Payer code
6. Number of medications
7. Time in hospital
8. Secondary diagnosis
9. Tertiary diagnosis
10. Insulin usage

---

## 🔍 Model Explainability

To improve model transparency, SHAP (SHapley Additive exPlanations) was used to interpret feature contributions.

SHAP analysis showed that:

- Previous inpatient admissions strongly increased readmission risk.
- Discharge disposition had the largest influence on predictions.
- Diagnosis codes contributed substantially to prediction.
- Healthcare utilization history significantly affected model decisions.

---

## 📂 Repository Structure

```
Hospital-Readmission-Prediction/
│
├── README.md
├── Hospital_Readmission_Prediction.ipynb
├── diabetic_data.csv
├── Hospital_Readmission_CatBoost_Model.cbm
├── Hospital_Readmission_Predictions.csv
├── feature_importance.csv
├── requirements.txt
└── images/
```

---

## 🚀 How to Run the Project

### Clone the repository

```bash
git clone https://github.com/yourusername/hospital-readmission-prediction.git
```

### Navigate to the project

```bash
cd hospital-readmission-prediction
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```
Hospital_Readmission_Prediction.ipynb
```

---

## 📁 Output Files

The notebook generates:

- Trained CatBoost model
- Feature importance CSV
- Hospital readmission predictions
- ROC Curve
- Precision-Recall Curve
- SHAP Summary Plot
- Confusion Matrix

---

## 📌 Key Findings

- Previous inpatient admissions were among the strongest predictors of readmission.
- Discharge disposition was the most influential feature.
- Diagnosis information significantly improved prediction performance.
- Medication burden and healthcare utilization history contributed to identifying high-risk patients.
- CatBoost outperformed all other evaluated machine learning models.

---

## 🔮 Future Improvements

Potential enhancements include:

- Hyperparameter optimization
- External validation using additional hospital datasets
- Integration of laboratory results and clinical notes
- Development of a real-time clinical decision support application
- Deployment as a web-based prediction tool

---

## 👨‍💻 Author

**Mohammad Sameer**

M.S. Health Informatics

Healthcare Data Analytics | Machine Learning | Clinical Informatics | Healthcare AI

LinkedIn: https://www.linkedin.com/in/sammoha/

---

## 📄 License

This project is intended for educational and research purposes. Please refer to the UCI Machine Learning Repository for dataset licensing and usage guidelines.
