# 📉 Telecom Customer Churn Prediction

### Machine Learning Classification Project

An end-to-end machine learning project that analyzes telecom customer behavior and predicts whether a customer is likely to churn.

The project explores customer characteristics, identifies factors associated with churn, compares multiple classification algorithms, and uses cross-validation and hyperparameter tuning to develop a predictive churn model.

---

## 📌 Project Overview

Customer churn is a major challenge for telecommunications companies. Identifying customers who are likely to leave can help businesses take proactive retention measures.

This project uses historical telecom customer data to build a binary classification model that predicts:

* `0` → Customer stays
* `1` → Customer churns

The project follows a complete machine learning workflow, including data exploration, preprocessing, model development, evaluation, cross-validation, and hyperparameter optimization.

---

## 🎯 Objectives

The main objectives of this project are to:

* Analyze customer characteristics associated with churn
* Explore relationships between customer behavior and churn
* Identify important predictive features
* Compare multiple classification algorithms
* Evaluate models using metrics beyond accuracy
* Address class imbalance
* Perform cross-validation
* Optimize model hyperparameters
* Identify a suitable model for customer churn prediction

---

## 📊 Dataset

The dataset contains **3,333 customer records** and **11 variables**.

### Target Variable

| Variable | Description                  |
| -------- | ---------------------------- |
| `Churn`  | Whether the customer churned |

### Features

| Feature           | Description                          |
| ----------------- | ------------------------------------ |
| `AccountWeeks`    | Length of customer relationship      |
| `ContractRenewal` | Contract renewal status              |
| `DataPlan`        | Whether the customer has a data plan |
| `DataUsage`       | Customer data usage                  |
| `CustServCalls`   | Number of customer service calls     |
| `DayMins`         | Daily call minutes                   |
| `DayCalls`        | Number of daily calls                |
| `MonthlyCharge`   | Monthly customer charge              |
| `OverageFee`      | Customer overage fee                 |
| `RoamMins`        | Roaming minutes                      |

The dataset contains **2,850 non-churned customers and 483 churned customers**, making class imbalance an important consideration during model evaluation.

---

## 🔎 Exploratory Data Analysis

The analysis investigated relationships between customer churn and variables including:

* Customer tenure
* Contract renewal
* Data plan usage
* Customer service calls
* Daily call minutes
* Monthly charges
* Overage fees
* Roaming usage

Key comparisons were performed between churned and non-churned customers to identify behavioral patterns that could help predict churn.

---

## 🧠 Machine Learning Workflow

The project follows this workflow:

```text
Raw Dataset
     ↓
Data Cleaning
     ↓
Exploratory Data Analysis
     ↓
Feature Analysis
     ↓
Train/Test Split
     ↓
Model Training
     ↓
Model Evaluation
     ↓
Cross-Validation
     ↓
Hyperparameter Tuning
     ↓
Final Model Evaluation
```

---

## 🤖 Models Evaluated

Multiple classification algorithms were implemented and compared:

* Logistic Regression
* Decision Tree
* Random Forest
* Bagging Classifier
* AdaBoost
* Gradient Boosting

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1 Score
* ROC-AUC
* PR-AUC
* Confusion Matrix

Because the dataset contains substantially more non-churned than churned customers, precision, recall, F1 and PR-AUC were considered alongside accuracy.

---

## 📈 Model Performance

### Baseline Model Comparison

| Model               |   Accuracy |  Precision |     Recall |         F1 |    ROC-AUC |
| ------------------- | ---------: | ---------: | ---------: | ---------: | ---------: |
| Logistic Regression |     85.76% |     52.63% |     20.62% |     29.63% |     58.73% |
| Decision Tree       |     89.21% |     64.04% |     58.76% |     61.29% |     76.57% |
| Random Forest       | **92.80%** | **81.82%** |     64.95% | **72.41%** | **81.25%** |
| Bagging             |     92.65% |     83.33% |     61.86% |     71.01% |     79.88% |
| Gradient Boosting   |     92.35% |     78.75% | **64.95%** |     71.19% |     80.98% |
| AdaBoost            |     87.41% |     63.27% |     31.96% |     42.47% |     64.40% |

Random Forest provided one of the strongest overall combinations of precision, recall, F1 score and ROC-AUC among the evaluated models.

---

## 🔧 Hyperparameter Tuning

`GridSearchCV` with stratified cross-validation was used to optimize the ensemble models.

### Random Forest

The tuned Random Forest search explored:

* Number of estimators
* Maximum tree depth
* Minimum samples required for splitting
* Minimum samples per leaf

The best Random Forest configuration achieved a cross-validation F1 score of approximately **0.762**.

### Gradient Boosting

Gradient Boosting hyperparameters were also optimized using GridSearchCV.

This allowed the project to compare baseline models against tuned models rather than relying only on default parameters.

---

## 📊 Final Model Evaluation

The tuned Random Forest achieved:

| Metric    |      Score |
| --------- | ---------: |
| Accuracy  | **92.35%** |
| Precision | **80.26%** |
| Recall    | **62.89%** |
| F1 Score  | **70.52%** |
| ROC-AUC   | **80.13%** |
| PR-AUC    | **74.61%** |

The results demonstrate that the model can identify a meaningful portion of potential churners while maintaining relatively strong precision.

---

## 💡 Business Interpretation

A churn prediction model can help telecom companies identify customers who may be at higher risk of leaving.

Potential business applications include:

* Targeted customer retention campaigns
* Proactive customer support
* Personalized offers
* Contract renewal strategies
* Identifying high-risk customer segments
* Prioritizing retention resources

The model should be viewed as a decision-support tool rather than a replacement for business judgment.

---

## 🛠️ Technologies

| Category              | Technologies                                                                            |
| --------------------- | --------------------------------------------------------------------------------------- |
| Programming           | Python                                                                                  |
| Data Analysis         | Pandas, NumPy                                                                           |
| Visualization         | Matplotlib, Seaborn                                                                     |
| Machine Learning      | Scikit-learn                                                                            |
| Classification        | Logistic Regression, Decision Tree, Random Forest, Bagging, AdaBoost, Gradient Boosting |
| Model Evaluation      | Precision, Recall, F1, ROC-AUC, PR-AUC                                                  |
| Model Selection       | Cross-Validation                                                                        |
| Hyperparameter Tuning | GridSearchCV                                                                            |
| Development           | Jupyter Notebook                                                                        |
| Version Control       | Git & GitHub                                                                            |

---

## 📂 Project Structure

```text
Telecom-Customer-Churn-Prediction/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── customer_churn_prediction.ipynb
│
├── data/
│   └── telecom_churn.csv
│
├── reports/
│   └── telecom_customer_churn_report.pdf
│
└── assets/
    ├── churn_distribution.png
    ├── model_comparison.png
    ├── confusion_matrix.png
    └── feature_importance.png
```

---

## 📄 Project Report

A detailed project report is available in:

```text
reports/telecom_customer_churn_report.pdf
```

---

## 🎓 Project Background

This project was developed as a machine learning classification project to apply supervised learning concepts to a real-world business problem.

The project demonstrates practical experience with data preprocessing, exploratory analysis, classification algorithms, model evaluation, cross-validation, and hyperparameter optimization.

---

## 👨‍💻 Author

**Muhammad Shaaf**

Data Science | Machine Learning | SQL | Python | Power BI

GitHub: [MuhammadShaaf](https://github.com/MuhammadShaaf)

---

## ⭐ Key Takeaway

This project demonstrates an end-to-end approach to customer churn prediction, from exploratory data analysis and feature investigation to model comparison, cross-validation, and hyperparameter tuning.
