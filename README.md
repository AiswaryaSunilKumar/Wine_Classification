
# Wine Quality Classification using Machine Learning

This project builds a Machine Learning classification system that predicts whether a wine is **Good** or **Bad** based on its physicochemical properties.
Using the **Red Wine Quality Dataset** from the UCI ML Repository, multiple ML models were trained, evaluated, compared, and optimized.
The project concludes with a highly accurate **Random Forest Classifier**, which achieved approximately **93% accuracy after oversampling and tuning**.

---

## Project Overview

The main objective of this project is to classify wines into:

* Good Wine (1)
* Bad Wine (0)

based on 11 chemical properties such as acidity, sugar, alcohol content, sulphates, etc.

The project covers:

* Data preprocessing and cleaning
* Exploratory Data Analysis (EDA)
* Comparison of 7 machine learning models
* Feature importance analysis
* Oversampling using SMOTE
* Hyperparameter tuning using RandomSearchCV
* Cross-validation
* Improving model accuracy by removing negatively correlated features

---

## Dataset

**Red Wine Quality Dataset – UCI ML Repository**

* Rows: 1599
* Features: 11 chemical properties
* Target: Wine quality (originally 3–8)
* Converted into binary classification:

  * 1 = Good (quality ≥ 7)
  * 0 = Bad (quality ≤ 6)

---

## Machine Learning Models Used

Seven ML algorithms were trained and evaluated:

| Model                    | Accuracy |
| ------------------------ | -------- |
| Random Forest Classifier | 0.893    |
| XGBoost                  | 0.891    |
| KNN                      | 0.872    |
| Logistic Regression      | 0.870    |
| SVM (RBF Kernel)         | 0.868    |
| Decision Tree            | 0.864    |
| Gaussian NB              | 0.833    |

### Best Model: Random Forest Classifier

Selected due to:

* High accuracy
* Stability
* Low variance due to ensembling
* Effective handling of feature interactions

---

## Exploratory Data Analysis (EDA)

Key findings:

* All features follow a normal distribution
* Alcohol content had the strongest positive correlation with quality
* pH was negatively correlated with multiple features
* Removing pH improved the model further

### Feature Importance (Top Features)

1. Alcohol – 17.15%
2. Volatile Acidity – 11.59%
3. Sulphates – 11.02%

---

## Handling Imbalanced Classes (SMOTE)

The dataset had an imbalance between Good and Bad wines.
SMOTE oversampling was applied.

| Stage        | Accuracy |
| ------------ | -------- |
| Before SMOTE | 89.58%   |
| After SMOTE  | 93.13%   |

---

## Hyperparameter Tuning

Performed using **RandomSearchCV** with:

* 10 iterations
* 3-fold cross-validation
* Random sampling of:

  * n_estimators
  * max_depth
  * min_samples_leaf
  * max_features

This resulted in improved accuracy compared to the base model.

---

## Removing Negatively Correlated Features

The feature **pH** was identified as negatively correlated with several key features.
After dropping pH, reapplying oversampling, and re-tuning, the accuracy increased further.

---

## Final Results

* Random Forest chosen as the final model
* Achieved strong accuracy after oversampling and tuning
* Identified key features influencing wine quality
* Completed a full pipeline: EDA, modeling, tuning, evaluation

---

