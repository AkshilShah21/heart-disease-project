# Heart Disease Classification - Portfolio Project

## Overview
This repository contains a machine learning project aimed at predicting whether an individual has heart disease based on clinical parameters. The focus of this project is to demonstrate skills in data analysis, model development, hyperparameter tuning, and model evaluation for a real-world health-related classification problem.


## Problem Statement
Heart disease is a leading cause of morbidity and mortality worldwide. Early detection of individuals at risk can significantly improve treatment outcomes and save lives. This project aims to classify whether an individual has heart disease, emphasizing the minimization of false negatives to ensure critical cases are not missed.


## Data
The dataset used for this project is the **Heart Disease Dataset** from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/heart+Disease). It contains clinical data on individuals, including features such as age, cholesterol levels, blood pressure, and exercise-induced angina. 


## Evalution Metric
The models are been not just on accuracy but also consider other metrics. For a problem where the goal is to classify whether someone has heart disease, false negatives (FN) are indeed more critical than false positives (FP). This is because failing to identify a person with heart disease could have severe consequences, while a false positive might lead to further tests, which are generally safer. \
Higher Recall ensures that FN is lower. Even though we care more about recall but we want precision high as well because if you want to reduce unnecessary follow-ups or tests.


## Model Selection Process

1. **Initial Model Evaluation**:  
   Four models were initially evaluated for their baseline performance using accuracy on the test set.

   | Model                 | Accuracy  |
   |-----------------------|-----------|
   | Logistic Regression   | 0.852459  |
   | SVC                   | 0.704918  |
   | KNN                   | 0.655738  |
   | Random Forest         | 0.885246  |

   - KNN exhibited the lowest accuracy and was discarded as it performed poorly compared to the other models.

2. **Hyperparameter Tuning**:  
   The remaining models underwent hyperparameter tuning to improve their performance.

   | Model                 | Accuracy (after tuning) |
   |-----------------------|--------------------------|
   | Logistic Regression   | 0.868852                |
   | SVC                   | 0.885246                |
   | Random Forest         | 0.868852                |

3. **Random Forest Evaluation**:  
   - Although Random Forest showed strong accuracy, it was significantly slower in training and prediction.
   - Given its computational cost and the lack of a clear advantage over Logistic Regression or SVC, Random Forest was excluded to prioritize real-time feasibility and efficiency.
  
## Model Evaluation

| Metric      | Logistic Regression | SVC       |
|-------------|----------------------|-----------|
| Precision   | 0.852941             | 0.878788  |
| Recall      | 0.90625              | 0.90625   |
| F1 Score    | 0.878788             | 0.892308  |
| AUC         | 0.941810             | 0.949353  |

### Key Findings:
1. **SVC** demonstrated a slightly higher performance compared to Logistic Regression in terms of AUC (0.95 vs. 0.94) and precision.
2. Both models achieved similar recall (91%), ensuring effectiveness in minimizing false negatives, which is critical for this problem.
3. **SVC's precision was slightly higher (by 3%)**, indicating fewer unnecessary follow-ups or false positives.
