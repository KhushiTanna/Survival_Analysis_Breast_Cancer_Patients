## Breast Cancer Survival Analysis using Logistic Regression & Cox PH Model

This project analyzes breast cancer patient data from the METABRIC breast cancer dataset to predict survival outcomes. It combines **Logistic Regression** and **Cox Proportional Hazards** models to assess both the likelihood and timing of survival events.

---

## Objective

- Estimate and compare survival probabilities using Kaplan-Meier curves.
- Identify significant risk factors affecting survival with **Cox Proportional Hazards** model.
- Predict binary outcomes (death/survival) using **Logistic Regression**.

---

## Dataset

**Source:** [METABRIC - Molecular Taxonomy of Breast Cancer]
- 2,507 patient records  
- 32 clinical, pathological, and molecular features  
- Time-to-event (survival months) and survival status included

---

## Technologies & Libraries Used

- `Python`, `pandas`, `numpy`, `matplotlib`, `seaborn`
- `scikit-learn`: Logistic Regression, preprocessing
- `lifelines`: Kaplan-Meier Estimator, Cox PH model
- `LabelEncoder`, `StandardScaler`

---

## Data Preprocessing

- Imputed missing values using **median** for numeric and **mode** for categorical features.
- Transformed categorical and interval features using:
  - `LabelEncoder` for object/ordinal columns
  - Converted `Interval` features (from `pd.cut`) to **midpoints**
- Standardized features using `StandardScaler`.

---

## Models Built

### Logistic Regression (Binary Classification)
- Target: `Overall Survival Status` (1 = died, 0 = survived)
- Evaluation:
  - Accuracy: **81%**
  - AUC: **0.889**
  - Precision (Class 1): 0.89
  - Recall (Class 1): 0.74

### Cox Proportional Hazards Model
- Target: `Overall Survival (Months)` with censoring
- Evaluated using:
  - Concordance Index (C-index): **0.875**
  - Partial AIC: **17253.20**
  - Key features affecting risk: Tumor size, Chemotherapy, Hormone therapy

---

## Visualizations

- ROC Curve for Logistic Regression
- Feature importance bar chart
- Kaplan-Meier survival curves
- Confusion matrix and classification report

---

## Results Summary

| Model              | Metric         | Score     |
|-------------------|----------------|-----------|
| Logistic Regression | Accuracy       | 81.07%    |
| Logistic Regression | AUC Score      | 0.889     |
| Cox PH Model       | Concordance     | 0.875     |
| Cox PH Model       | Partial AIC     | 17253.20  |

---

## Interpretation

- Logistic Regression performed well at **classifying** patients based on death risk.
- Cox PH was more useful for **ranking patients by survival time** and identifying **prognostic features**.
- Features like **chemotherapy**, **hormone therapy**, and **tumor size** had strong influence on outcomes.

---


