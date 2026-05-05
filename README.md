# customer-churn-model
# Customer Churn Prediction Model

## Overview
This project builds an end-to-end machine learning pipeline to predict customer churn 
for a subscription-based business. By identifying high-risk customers before they leave, 
businesses can take targeted retention actions and reduce revenue loss.

---

## Problem Statement
Customer churn is a critical metric for any subscription or service-based business. 
This model uses historical customer data to classify whether a customer is likely to 
churn, enabling proactive intervention.

---

## Tech Stack
- **Language:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn, XGBoost
- **Notebook:** Jupyter Notebook
- **Version Control:** Git & GitHub

---

## Dataset
- **Source:** IBM Telco Customer Churn Dataset (via Kaggle)
- **Size:** 7,043 rows, 20 features
- **Target variable:** `Churn` (Binary: Yes / No)

Key features included: contract type, tenure, monthly charges, payment method, 
internet service type, and customer support interactions.

---

## Methodology

### 1. Exploratory Data Analysis (EDA)
- Analyzed churn rate distribution and class imbalance
- Identified key correlations between features and churn behavior
- Visualized tenure, contract type, and monthly charges as top churn drivers

### 2. Data Preprocessing
- Handled missing values and outliers
- Encoded categorical variables (Label Encoding / One-Hot Encoding)
- Scaled numerical features using StandardScaler
- Addressed class imbalance using SMOTE

### 3. Model Building
Trained and compared multiple classification models:
| Model | Accuracy | Precision | Recall | F1 Score |
|---|---|---|---|---|
| Logistic Regression | 79% | 64% | 71% | 67% |
| Random Forest | 83% | 70% | 73% | 71% |
| XGBoost | 87% | 76% | 80% | 78% |

### 4. Model Evaluation
- Primary metric: **Recall** (minimizing false negatives / missed churners)
- Used confusion matrix, ROC-AUC curve, and classification report
- Final model: **XGBoost** with ROC-AUC of 0.88

### 5. Feature Importance
Top predictors of churn identified:
1. Contract type (month-to-month customers churn significantly more)
2. Tenure (newer customers have higher churn risk)
3. Monthly charges
4. Number of customer service calls

---

## Key Findings
- Customers on **month-to-month contracts** were 3x more likely to churn
- High monthly charges combined with short tenure was the strongest churn signal
- Customers without tech support or online security showed elevated churn rates
