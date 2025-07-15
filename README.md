# Diabetes-Patient-Readmitted-Prediction
This project aims to predict whether a diabetic patient will be readmitted to the hospital within 30 days using structured Electronic Health Record (EHR) data. The goal is to help healthcare providers identify high-risk patients and take preventive action.

# Dataset
Source: UCI Machine Learning Repository
Records: ~100,000+ hospital admissions
Target Variable: readmitted (NO / <30 / >30)
Features:
Demographics (age, gender, race)
Clinical measurements (lab results, diagnoses, medications)
Hospitalization info (number of inpatient visits, discharge disposition, etc.)

# Key Steps
# Data Preprocessing
Removed irrelevant and high-cardinality columns (e.g., encounter_id, patient_nbr)
Handled missing values in race, weight, payer code, and medical specialty
Encoded categorical variables (diagnoses, gender, etc.)
Mapped target variable to binary (readmitted within 30 days = 1, otherwise 0)
Standardized numerical features for model compatibility

# Feature Engineering
Derived new features like number of chronic conditions and medication changes

Handled class imbalance using SMOTE

Grouped ICD-9 codes into broader disease categories

# Modeling
# Algorithms Used:
Logistic Regression
Random Forest
Support Vector Machine (SVM)
XGBoost
K-Nearest Neighbors
Voting Classifier (Ensemble)
# Evaluation Metrics:
Accuracy
Precision
Recall
F1-Score
ROC-AUC
Confusion Matrix
Cross-validation for generalization

# Unsupervised Learning
PCA for dimensionality reduction 
KMeans clustering for patient segmentation
Silhouette score to evaluate cluster quality

# Results
Best Model(s): XGBoost, Random Forest

ROC-AUC Scores: 0.84 – 0.88

Key Insight: Prior hospital visits, insulin usage, and certain diagnosis groups were strong predictors of readmission

# Project Structure
bash
Copy
Edit
diabetes_readmission.ipynb      # Main Jupyter notebook
diabetic_data.csv               # Raw dataset
README.md                       # Project overview
requirements.txt                # Dependencies and libraries
