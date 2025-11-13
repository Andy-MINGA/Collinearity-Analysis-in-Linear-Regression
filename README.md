# 📊 Collinearity Analysis in Linear Regression
This project explores **collinearity** in multiple linear regression using simulated data, examining its effect on coefficient estimates, hypothesis testing, and model interpretation.


---

## 🔹 Objective
To demonstrate how correlated predictors affect regression estimates, hypothesis testing, and model interpretation.

---

## 🔹 Linear Model

The simulated model is:

$$
y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \varepsilon
$$

Where:  
- $\beta_0 = 2$ (intercept)  
- $\beta_1 = 2$ (coefficient of $x_1$)  
- $\beta_2 = 0.3$ (coefficient of $x_2$)  
- $\varepsilon \sim \mathcal{N}(0, \sigma^2)$  

Full model:

$$
y = 2 + 2x_1 + 0.3x_2 + \varepsilon
$$

---

## 🔹 Correlation Analysis

- Correlation between $x_1$ and $x_2$: **0.7723**  
- Scatterplot shows strong positive correlation (collinearity).

---

## 🔹 Multiple Regression (`y ~ x1 + x2`)

Estimated model:

$$
\hat{y} = \hat{\beta}_0 + \hat{\beta}_1 x_1 + \hat{\beta}_2 x_2
$$

| Coefficient | True Value | Estimated Value | Interpretation |
|------------|------------|----------------|----------------|
| $\beta_0$ | 2.0        | 1.9579         | Very close to true value |
| $\beta_1$ | 2.0        | 1.6154         | Underestimated due to collinearity |
| $\beta_2$ | 0.3        | 0.9428         | Overestimated due to collinearity |

**Hypothesis Testing:**  
- $H_0: \beta_1 = 0$ → p-value < 0.05 → **reject null** → $x_1$ is significant  
- $H_0: \beta_2 = 0$ → p-value > 0.05 → **fail to reject** → $x_2$ is not significant when $x_1$ is included

---

## 🔹 Simple Regression Models

**1. Using only $x_1$:**

$$
\hat{y} = \hat{\beta}_0 + \hat{\beta}_1 x_1 = 1.9371 + 2.0771 \cdot x_1
$$

- Close to true coefficients  
- Captures linear relationship accurately  
- p-value for $\hat{\beta}_1$ < 0.05 → significant predictor

**2. Using only $x_2$:**

$$
\hat{y} = \hat{\beta}_0 + \hat{\beta}_2 x_2 = 2.3239 + 2.9103 \cdot x_2
$$

- p-value < 0.05 → significant  
- Suffers from **omitted variable bias** because $x_2$ is highly correlated with $x_1$  
- Estimated effect of $x_2$ is **biased**  

---

## 🔹 Interpretation

- Model (c) [$x_1$ + $x_2$]: unbiased, less stable due to multicollinearity  
- Model (d) [$x_1$ only]: more accurate, stable, captures main signal  
- Model (e) [$x_2$ only]: biased due to omitted variable ($x_1$)  
- Highlights trade-off between **model correctness** and **coefficient stability**

---

## 🔹 Influence of New Observation

Added observation: $(x_1=0.1, x_2=0.8, y=6)$

| Model | Observation Type | Influence |
|-------|----------------|-----------|
| $y \sim x_1 + x_2$ | Outlier & High-Leverage | Large influence on model |
| $y \sim x_1$      | Outlier only       | Moderate influence |
| $y \sim x_2$      | Outlier & High-Leverage | Large influence |

- The new point is **most influential** in models including $x_2$, less so for $x_1$-only model.

---

## 🔹 Key Insights

- Strong correlation between predictors inflates standard errors and distorts estimates  
- Omitting variables in correlated datasets causes **bias**  
- Single influential points can dramatically alter regression outcomes, especially with multicollinearity

---

## 🔹 Conclusion

- Collinearity affects regression estimates and hypothesis tests  
- Model choice and variable inclusion are crucial to balance **accuracy** and **stability**  
- Diagnostic checks for multicollinearity and influential points are essential in regression analysis
