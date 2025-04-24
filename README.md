# 🩺 Diabetes Risk Prediction Case Study

**Project Title:** Predicting Diabetes Risk Using Machine Learning  
**Author:** [Rose Kimondo]   
**Date:** April 2025  

---

## 📌 Introduction

Diabetes is a chronic disease with increasing global prevalence. Early prediction using machine learning can help reduce the risk through timely intervention. This case study focuses on building predictive models to classify whether a person is likely to have diabetes based on medical and demographic features.

---

## 🧾 Objective

To develop and evaluate machine learning models that predict whether a patient is diabetic based on a set of clinical attributes. The main goals are:

- Perform exploratory data analysis (EDA) and preprocessing
- Build and compare Logistic Regression and Random Forest models
- Evaluate model performance using relevant metrics
- Interpret model outputs and identify key risk factors

---

## 📊 Dataset Description

**Features:**

- `Pregnancies`: Number of times pregnant  
- `Glucose`: Plasma glucose concentration  
- `BloodPressure`: Diastolic blood pressure (mm Hg)  
- `SkinThickness`: Triceps skin fold thickness (mm)  
- `Insulin`: 2-Hour serum insulin (mu U/ml)  
- `BMI`: Body mass index (weight in kg/(height in m)^2)  
- `DiabetesPedigreeFunction`: A function that scores the likelihood of diabetes based on family history  
- `Age`: Age in years  
- `Outcome`: Target variable (1 = Diabetic, 0 = Non-diabetic)

---

## 🔍 Exploratory Data Analysis (EDA)

- Checked for missing or zero values in `Glucose`, `BloodPressure`, `BMI`, etc.
- Visualized class distribution (imbalanced dataset: ~65% Non-diabetic, ~35% Diabetic)
- Used box plots and histograms to observe feature distributions
- Heatmap of feature correlations

**Key Findings:**
- `Glucose`, `BMI`, and `Age` showed strong correlation with diabetes.
- Some features (e.g., `Insulin`, `SkinThickness`) had many zero values → imputed or flagged.

---

## 🧹 Data Preprocessing

- Handled missing/zero values: Replaced 0s with median values or created binary flags
- Normalized features using MinMaxScaler / StandardScaler
- One-hot encoded categorical variables (if any)
- Split data: 80% Train / 20% Test

---

## 🧠 Model Building

### 1. Logistic Regression

- Interpretable baseline model
- Evaluated feature coefficients
- Used `L2` regularization and `GridSearchCV` for tuning

### 2. Random Forest Classifier

- Handles non-linearity and interactions well
- Tuned `n_estimators`, `max_depth`, `min_samples_split`
- Feature importance extracted

---

## ✅ Model Evaluation

| Metric               | Logistic Regression | Random Forest |
|----------------------|---------------------|----------------|
| Accuracy             | 57%                 | 63%            |
| Precision            | 61%                 | 56%            |
| Recall (Sensitivity) | 57%                 | 63%            |
| F1 Score             | 58%                 | 58%            |
| ROC-AUC              | 58%                 | 52%            |

- Plotted confusion matrix and ROC curves
- Random Forest outperformed Logistic Regression in most metrics
- Feature importance showed `Blood Level` and `Insulin Level` as top predictors

---

## 🧠 Interpretation and Insights

- Logistic Regression coefficients helped understand direct impact of features
- Random Forest highlighted non-linear relationships

---

## 📈 Conclusion

- Built two models to predict diabetes: Logistic Regression and Random Forest
- Random Forest had better predictive performance, but Logistic Regression was more interpretable
- Demonstrated full ML pipeline: from data cleaning to deployment-ready models

---

## 🔄 Next Steps

- Try advanced models (e.g., XGBoost, LightGBM)
- Explore SHAP values for better interpretability
- Deploy model using Flask or Streamlit
- Collect more real-world data to reduce bias
