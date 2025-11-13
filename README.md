# Collinearity-Analysis-in-Linear-Regression
This project explores the effect of collinearity in multiple linear regression using simulated data.


# 📈 Collinearity Analysis in Linear Regression

This project explores the effect of **collinearity** in multiple linear regression using simulated data.

---

## 🔹 Objective
To demonstrate how correlated predictors affect regression estimates, hypothesis testing, and model interpretation.

---

## 🔹 Overview

- A dataset was simulated with two predictors, `x1` and `x2`, and a response variable `y` defined by:

\[
y = 2 + 2x_1 + 0.3x_2 + \varepsilon
\]

- `x2` is partially dependent on `x1`, introducing **multicollinearity**.  
- The analysis examines how collinearity affects regression coefficients, statistical significance, and model interpretation.

---

## 🔹 Analysis Steps

1. **Correlation Analysis**  
   - Calculated the correlation between `x1` and `x2`.  
   - Visualized their relationship using a scatterplot.

2. **Multiple Regression (`y ~ x1 + x2`)**  
   - Fitted a multiple linear regression model.  
   - Estimated coefficients were compared to the true values (2, 2, 0.3).  
   - Hypotheses tested:  
     - \( H_0: \beta_1 = 0 \)  
     - \( H_0: \beta_2 = 0 \)

3. **Simple Regressions**  
   - Fitted models using only `x1` and only `x2`.  
   - Observed the effects of collinearity on coefficient estimates and significance.

4. **Influential Observation Analysis**  
   - Introduced one mismeasured data point.  
   - Re-fitted all models to assess the effect.  
   - Determined whether the new observation acted as an **outlier**, **high-leverage point**, or **both**.

---

## 🔹 Key Insights

- Strong correlation between predictors inflates variance of estimated coefficients.  
- Collinearity can lead to conflicting significance results between single and multiple regressions.  
- A single influential observation can heavily affect regression results, particularly in models with multicollinearity.

---

## 🔹 Conclusion

This analysis highlights the importance of diagnosing **multicollinearity** and identifying **influential points** in regression modeling to ensure reliable and interpretable results.

---

## 🔹 Dependencies

- Python 3.x  
- NumPy  
- matplotlib / seaborn  
- statsmodels  

---

## 🔹 Files

- `collinearity_analysis.ipynb` — notebook with full analysis and visualizations  
- `README.md` — project overview and instructions

