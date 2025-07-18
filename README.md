# Employee Satisfaction & Attrition Prediction

A data science project focused on predicting employee **job satisfaction** and **attrition risk** using supervised machine learning techniques. This project delivers insights for HR departments to take proactive action and reduce staff turnover.

---

## Project Objectives

- **Objective 1:** Develop a model to predict employee **job satisfaction**
- **Objective 2:** Build a classifier to predict the **likelihood of employee attrition**

---

## Data Preprocessing

- Cleaned missing values and handled both **explicit and implicit duplicates**
- Corrected inconsistent categorical entries (e.g., typo in `level`)
- Applied **feature encoding** (`OneHotEncoder`, `OrdinalEncoder`) and **scaling** to prepare data for modeling

---

## Exploratory Data Analysis (EDA)

Key insights from the data:

- **Average salary**: ~34,000 RUB per month  
  → Applied **log transformation** due to left-skewed distribution
- Most employees have **< 5 years of tenure**
- **Average supervisor evaluation** ≈ 4/5
- **Department breakdown**:
  - Sales: 37%
  - Technical: 22%
  - Marketing & Procurement: ~15%
  - HR: 12%
- Strong predictors:
  - **Supervisor evaluation**
  - **Policy violations**
  - **Salary**
  - **Workload**

---

## Job Satisfaction Prediction

- **Model**: `DecisionTreeRegressor`
- **Target metric**: SMAPE ≤ 15%
- **Residual analysis** confirmed stable predictions
- Model achieved target performance on test data

### Key Drivers of Satisfaction

- **↑ Supervisor rating > 3** → +0.16 satisfaction
- **↑ Tenure** → ↑ satisfaction
- **↑ Job level** → ↓ satisfaction
- **↑ Salary** → ↑ satisfaction
- **Policy violations** and **high workload** → ↓ satisfaction
- **Sales** department → ↑ satisfaction  
  **Technical** department → ↓ satisfaction

> **Supervisor evaluation** is the most influential feature.

---

## Attrition Prediction

- **Model**: `DecisionTreeClassifier` with hyperparameter tuning
- Addressed **class imbalance** with oversampling
- Incorporated **predicted satisfaction** as a feature
- Used **SHAP values** for feature selection
- Achieved target **ROC AUC score** on test set

---

## Business Recommendations

- Use models to:
  - Proactively identify **at-risk employees**
  - Launch **retention interventions**
- Investigate high attrition in **senior-level staff**
- Implement programs to **improve satisfaction**
- Monitor and manage **employee workload**
- Use insights to develop a **data-driven HR strategy**
