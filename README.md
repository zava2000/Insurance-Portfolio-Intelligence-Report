# Insurance-Portfolio-Intelligence-Report

### A Data-Driven Approach to Risk Analysis

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Library](https://img.shields.io/badge/Library-Scikit--Learn-orange)
![Library](https://img.shields.io/badge/Library-Pandas-150458)
![Status](https://img.shields.io/badge/Status-Completed-green)

**Author:** Agustin A. Zavagnini  
**Date:** November 2025

---

## 📋 Executive Summary
The primary objective of this project is to develop a predictive model for individual medical insurance costs based on demographic and lifestyle variables. Accurately forecasting medical expenses is critical for insurance companies to maintain profitability while offering competitive premiums, and for policyholders to understand their financial risk exposure.

Using a dataset of 1,338 beneficiaries, this project moves from Exploratory Data Analysis (EDA) to Statistical Inference (OLS Regression) and finally to Machine Learning (Random Forest), achieving an **$R^2$ of 0.85**.

---

## 💡 Key Business Insights
Based on the analysis, the following actionable insights were derived for actuarial and risk teams:

1.  **Smoking is the #1 Cost Driver:** Being a smoker is the single most critical factor in predicting costs, outweighing all demographic factors combined. Smokers incur costs **3x to 4x higher** than non-smokers.
2.  **The "Obesity Multiplier":** BMI alone has a moderate impact. However, the combination of **Smoking + High BMI (Obesity)** creates a compounding risk effect, leading to the highest costs in the dataset (> $30k USD).
3.  **Age Progression:** Medical costs increase linearly with age, representing a predictable baseline risk.
4.  **Demographics are Secondary:** Gender and Geographical Region showed no statistically significant impact on costs after controlling for lifestyle factors.

---

## 📊 Project Methodology

### 1. Exploratory Data Analysis (EDA)
We utilized **Seaborn** and **Plotly (Cufflinks)** to create static and interactive visualizations.
* **Distribution Analysis:** Identified a right-skewed distribution in charges and BMI.
* **Outlier Detection:** Decided to retain high-cost outliers as they represent valid high-risk business cases (e.g., chronic illnesses).
* **Multivariate Analysis:** Uncovered the non-linear interaction between smoking status and BMI.

![Analysis Dashboard](images/dashboard_preview.png)
*(Placeholder: Add a screenshot of your Dashboard 3 here)*

### 2. Statistical Analysis (OLS Regression)
We fit a multivariate linear regression model using `statsmodels` to test statistical significance.
* **Findings:** Confirmed that *Smoker*, *Age*, *BMI*, and *Children* are statistically significant ($p < 0.05$).
* **Diagnostics:** Residual analysis indicated non-normality, suggesting that a linear model was insufficient to capture complex interactions, prompting the move to Random Forest.

### 3. Machine Learning Modeling
We deployed a **Random Forest Regressor** to handle non-linearity and outliers.
* **Train/Test Split:** 70/30.
* **Estimators:** 300 Trees.

---

## 📈 Model Performance
The Random Forest model outperformed the linear baseline, successfully capturing the complex risk structures.

| Metric | Score | Interpretation |
| :--- | :--- | :--- |
| **$R^2$ Score** | **0.8543** | The model explains **85.4%** of the variability in medical charges. |
| **RMSE** | **$4,621** | Average deviation from the actual cost (sensitive to outliers). |
| **MAE** | **$2,617** | The average absolute error for a typical prediction. |

### Feature Importance
The model confirmed the findings from the EDA, ranking the features by predictive power:
1.  **Smoker Status** (~61%)
2.  **BMI** (~21%)
3.  **Age** (~14%)
4.  Others (< 5%)

---

## 🛠️ Technologies Used
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Visualization:** Matplotlib, Seaborn, Plotly, Cufflinks
* **Statistical Analysis:** Statsmodels
* **Machine Learning:** Scikit-learn (RandomForestRegressor)

-----

*This project was developed for educational and portfolio purposes to demonstrate end-to-end data analysis and modeling workflows.*
