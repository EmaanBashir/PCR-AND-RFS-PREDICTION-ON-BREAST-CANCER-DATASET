# Breast Cancer Outcome Prediction

## Overview

This repository contains the code and report for a semester project completed as part of my MSc in Data Science. The project focuses on predicting breast cancer treatment outcomes, specifically Pathological Complete Response (PCR) and Relapse-Free Survival (RFS), using machine learning techniques. The dataset consists of clinical and MRI-based features, and various models were evaluated to identify the best-performing approach.

## Table of Contents

- [Project Description](#project-description)
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [Preprocessing](#preprocessing)
- [Feature Selection](#feature-selection)
- [Machine Learning Models](#machine-learning-models)
- [Evaluation](#evaluation)
- [Requirements](#requirements)
- [Installation and Usage](#installation-and-usage)
- [Results](#results)
- [Presentation and Report](#presentation-and-report)

## Project Description

The goal of this project is to develop predictive models for PCR and RFS in breast cancer patients. The dataset includes 10 clinical features and 107 MRI-based features. Various preprocessing techniques, feature selection methods, and machine learning models were explored to improve prediction accuracy. The best model was selected based on performance metrics such as F1-score for classification and R-squared score for regression.

## Technologies Used

- Python
- Jupyter Notebook
- Scikit-Learn
- Pandas & NumPy
- Matplotlib & Seaborn

## Dataset

- The dataset was obtained from the American College of Radiology Imaging Archive.
- It contains **400 samples** with 10 clinical features and 107 MRI-based features.
- The dataset is highly imbalanced, with 78% negative and 22% positive samples for PCR.

## Preprocessing

- **Missing Values Handling:**
  - Removed rows with missing target values.
  - Median imputation for numerical features.
- **Data Balancing:**
  - Synthetic Minority Over-sampling Technique (SMOTE) was applied.
- **Feature Scaling:**
  - Standard scaling for SVM and MLP classifiers.

## Feature Selection

- **Random Forest Feature Importance**
- **Analysis of Variance (ANOVA)**
- **Pearson Correlation**
- **Principal Component Analysis (PCA)** (though it did not improve performance)

## Machine Learning Models

### Classification (PCR Prediction)

- **Random Forest**
- **XGBoost** *(Best performing model)*
- **SVM**
- **MLP**

### Regression (RFS Prediction)

- **Support Vector Regression (SVR)**
- **Random Forest Regression**
- **XGBoost Regression** *(Best performing model)*

## Evaluation

### Classification Metrics

- Macro Average F1-Score
- ROC Curve & AUC
- t-test for statistical validation of model performance

### Regression Metrics

- R-squared Score
- Mean Absolute Error (MAE)
- Cross-validation (5-fold)

## Requirements

To run this project, ensure you have the following dependencies installed:

```bash
pip install numpy pandas scikit-learn xgboost matplotlib seaborn
```

## Installation and Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/EmaanBashir/PCR-AND-RFS-PREDICTION-ON-BREAST-CANCER-DATASET.git
   ```
2. Navigate to the project folder:
   ```bash
   cd PCR-AND-RFS-PREDICTION-ON-BREAST-CANCER-DATASET/Code
   ```
3. Open the Jupyter notebooks in the `Task2_Classification/` and `Task2_Regression/` folders to explore preprocessing, feature selection, and model training.

## Results

### Classification Performance

| Model         | F1-Score        |
| ------------- | --------------- |
| SVM           | 0.43 - 0.56     |
| Random Forest | 0.43 - 0.49     |
| **XGBoost**   | **0.54 - 0.55** |

**Best Model:** XGBoost achieved the best F1-score and was validated through statistical testing. However, the scores indicate moderate performance, and further improvements (such as better feature engineering and handling class imbalance) may be needed to enhance classification accuracy.

### Regression Performance (XGBoost)

| Feature Selection Method             | R2 Score  | MAE       |
| ------------------------------------ | --------- | --------- |
| No Feature Selection                 | 0.043     | 20.86     |
| ANOVA Threshold 3                    | 0.086     | 20.32     |
| ANOVA Threshold 3 + Outlier Handling | **0.099** | **20.26** |

**Regression Observations:** The R² scores remain low, indicating that the model does not explain much variance in the target variable. While feature selection and outlier handling improved performance slightly, further refinement is required to enhance predictive accuracy.

**Future Improvements:**

- Enhanced Feature Engineering: Investigating additional transformations or domain-specific features.

- Alternative Machine Learning Models: Trying more sophisticated deep learning or ensemble techniques.

- More Data: Increasing the dataset size to improve generalization.

- Better Handling of Class Imbalance: Experimenting with different oversampling and undersampling methods.

## Presentation and Report
For more details, refer to the project presentation and report:

[Presentation Link](https://drive.google.com/file/d/1--Ok0PIHsByunCXKXtdemwg7g5ySjQWp/view?usp=drive_link)

[Report Link](Report.pdf)

