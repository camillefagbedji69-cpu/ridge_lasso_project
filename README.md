# Carbon-Regularization: Ridge vs Lasso in Environmental Modeling

## 📌 Context & Overview
In high-dimensional ecological datasets, multicollinearity between predictors (NDVI, LST, Land Use) often destabilizes standard Ordinary Least Squares (OLS) regression. This project explores the **Stein’s Paradox**—the idea that biased estimators can yield more accurate predictions than unbiased ones. We benchmark **Ridge (L2)** and **Lasso (L1)** regularization techniques against classical linear regression to optimize carbon stock estimation.

## 🎯 Objectives
* **Model Optimization:** Evaluating the impact of shrinkage on predictive accuracy (RMSE).
* **Bias-Variance Trade-off:** Demonstrating how regularization handles collinearity in environmental variables.
* **Performance Benchmarking:** Comparing OLS with variable selection versus penalized regressions using the full feature set.

## 🛠️ Tech Stack & Methodology
* **Language:** Python 3.13 
* **Framework:** `scikit-learn`, `scipy`.
* **Preprocessing:** Min-Max Scaling and Correlation-based feature selection for OLS.
* **Models Compared:**
    1. **OLS (Ordinary Least Squares):** Linear regression using a subset of highly correlated features ($|r| > 0.45$).
    2. **Ridge Regression (L2):** Penalizing the square of coefficients to handle multicollinearity.
    3. **Lasso Regression (L1):** Promoting sparsity by penalizing the absolute value of coefficients.



## 🚀 Key Results
* **Ridge Superiority:** The Ridge model achieved the lowest error (**RMSE: 15,087.31**), significantly outperforming the classical OLS (**RMSE: 22,099.53**). This confirms that L2 regularization is highly effective at stabilizing predictions when predictors are correlated.
* **Lasso Behavior:** The Lasso model showed limited discrimination in this specific dataset, likely converging to a trivial solution due to extreme collinearity or suboptimal alpha tuning.
* **Statistical Insight:** The experiment validates the use of "shrinkage" estimators in ecological modeling, proving that a controlled introduction of bias can lead to much more robust predictive performance.

## 🔮 Perspectives for Improvement
* **Hyperparameter Tuning:** Implementing `LassoCV` and `RidgeCV` to find the optimal regularization strength ($\alpha$) via cross-validation.
* **Elastic Net:** Testing a hybrid L1/L2 approach to combine the feature selection of Lasso with the stability of Ridge.
* **Collinearity Analysis:** Using Variance Inflation Factor (VIF) to further investigate why Lasso struggled compared to Ridge in this context.

---
*Statistical Excellence: Mastering the Bias-Variance Trade-off for Earth Observation.*
