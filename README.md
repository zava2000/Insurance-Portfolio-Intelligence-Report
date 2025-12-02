# 🩺 Insurance-Portfolio-Intelligence-Report

### A Data-Driven Approach to Medical Cost Risk Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Library](https://img.shields.io/badge/Library-Pandas-150458)
![Status](https://img.shields.io/badge/Status-Completed-green)

---

## 📋 Executive Summary

This project analyzes medical insurance charges to identify the demographic and behavioral factors that most strongly influence individual healthcare costs. Accurate cost forecasting is essential for insurers to design sustainable pricing strategies, manage portfolio risk, and anticipate high-cost claimants.

Using a dataset of **1,338 beneficiaries**, the project progresses through:

* **Exploratory Data Analysis (EDA)**
* **Statistical Modeling (OLS Regression)**
* **Machine Learning (Random Forest)**

The final model achieves an **$R^2$ of 0.85**, demonstrating strong predictive capability.

---

## 💡 Key Business Insights

Insights extracted from the analysis provide clear, actionable guidelines for risk and actuarial teams:

1. **Smoking Is the Dominant Cost Driver**
   Smokers represent the highest-risk segment, with medical charges **3×–4× higher** than non-smokers — the single strongest predictor across all models.

2. **The Obesity Multiplier Effect**
   BMI alone has a modest impact, but *high BMI + smoking* creates a compounding risk pattern. This group represents the **largest and most consistent high-cost profile** (>$30k USD).

3. **Age as a Linear Risk Contributor**
   Costs rise steadily with age, forming a predictable baseline pattern for portfolio pricing.

4. **Demographics Show Minimal Impact**
   Gender and region have little to no predictive power when lifestyle factors are included — valuable for simplifying pricing models.

![Feature Importance](https://github.com/zava2000/Insurance-Portfolio-Intelligence-Report/blob/main/Images/Feature%20Importance.png)

---

## 📊 Project Methodology

### **1. Exploratory Data Analysis (EDA)**

Tools: **Seaborn**, **Matplotlib**, **Plotly/Cufflinks**
Key findings include:

* **Charges and BMI** show right-skewed distributions.
* Outliers represent genuine high-risk cases and were retained.
* Strong **interaction effects** identified between smoking status and BMI.

![EDA Dashboard](https://github.com/zava2000/Insurance-Portfolio-Intelligence-Report/blob/main/Images/Dashboard%203.png)

---

### **2. Statistical Analysis (OLS Regression)**

A multivariate linear model (using `statsmodels`) was used to evaluate significance.

* Significant predictors: **Smoker**, **Age**, **BMI**, **Children**
* Residual diagnostic plots revealed deviations from normality
* The non-linear nature of interactions motivated the shift to a tree-based model

---

### **3. Machine Learning Modeling**

Model: **Random Forest Regressor**
Configuration:

* **Train/Test split:** 70/30
* **n_estimators:** 300
* Handles non-linearity, outliers, and feature interactions effectively.

---

## 📈 Model Performance

The Random Forest model successfully captures the underlying risk patterns in the portfolio.

| Metric    | Score      | Interpretation                                           |
| --------- | ---------- | -------------------------------------------------------- |
| **$R^2$** | **0.8543** | Explains 85.4% of the variance in medical charges.       |
| **RMSE**  | **$4,621** | Sensitive to large claims; acceptable for cost modeling. |
| **MAE**   | **$2,617** | Typical expected deviation in dollar terms.              |

### 🔍 Feature Importance (Random Forest)

1. **Smoker** (~61%)
2. **BMI** (~21%)
3. **Age** (~14%)
4. All others: <5%

This ranking aligns with the statistical findings and reinforces the EDA conclusions.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**, **NumPy**
* **Matplotlib**, **Seaborn**, **Plotly**, **Cufflinks**
* **Statsmodels**
* **Scikit-learn** (RandomForestRegressor)

---

### 📚 Project Purpose

This project was developed as part of a portfolio to demonstrate end-to-end analytical capabilities, from data preparation to business insight generation and predictive modeling.
