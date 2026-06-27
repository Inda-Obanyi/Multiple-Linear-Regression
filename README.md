# 📊 Multiple Linear Regression – Multi-Channel Marketing Analysis

## Project Overview

This project investigates how different marketing channels influence product sales using **Multiple Linear Regression (MLR)**. The analysis aims to determine the impact of advertising expenditures on:

* 📺 TV Advertising
* 📻 Radio Advertising
* 📱 Social Media Advertising

Using Python and the `statsmodels` library, we build and evaluate a multiple regression model that predicts sales based on marketing investments and provides business recommendations for optimizing advertising budgets.

---

# 🎯 Project Objectives

The objectives of this project are to:

* Perform Exploratory Data Analysis (EDA) on the marketing dataset.
* Examine relationships among predictor variables.
* Detect and address multicollinearity using:

  * Correlation Matrix
  * Variance Inflation Factor (VIF)
* Build a Multiple Linear Regression model using Ordinary Least Squares (OLS).
* Validate model assumptions through diagnostic plots.
* Interpret model coefficients in a business context.
* Generate actionable marketing recommendations based on findings.

---

# 📁 Dataset Description

The dataset contains advertising expenditure across three marketing channels and corresponding sales figures.

| Variable     | Description                              |
| ------------ | ---------------------------------------- |
| TV           | Advertising budget spent on Television   |
| Radio        | Advertising budget spent on Radio        |
| Social Media | Advertising budget spent on Social Media |
| Sales        | Product sales generated                  |

---

# 🛠️ Technologies Used

* Python 3.x
* Jupyter Notebook
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Statsmodels
* Scikit-learn

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/multi-channel-marketing-analysis.git
cd multi-channel-marketing-analysis
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or using Anaconda:

```bash
conda install pandas numpy matplotlib seaborn scikit-learn statsmodels
```

---

# 📚 Required Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

import statsmodels.api as sm
from statsmodels.stats.outliers_influence import variance_inflation_factor
```

---

# 🔎 Step 1: Exploratory Data Analysis (EDA)

The initial analysis focuses on:

* Understanding dataset dimensions
* Checking missing values
* Generating descriptive statistics
* Visualizing distributions
* Investigating relationships between variables

### Sample Commands

```python
df.head()
df.info()
df.describe()
df.isnull().sum()
```

---

# 📈 Step 2: Correlation Analysis

Correlation analysis helps determine the strength of relationships among variables.

```python
corr = df.corr()

plt.figure(figsize=(8,6))
sns.heatmap(corr,
            annot=True,
            cmap='coolwarm',
            fmt='.2f')
plt.title('Correlation Matrix')
plt.show()
```

### Interpretation

* Values close to +1 indicate strong positive relationships.
* Values close to -1 indicate strong negative relationships.
* Values close to 0 indicate weak relationships.

---

# 🔍 Step 3: Checking Multicollinearity Using VIF

Variance Inflation Factor (VIF) measures how strongly independent variables are correlated with one another.

```python
X = df[['TV', 'Radio', 'Social Media']]

vif = pd.DataFrame()
vif["Feature"] = X.columns
vif["VIF"] = [variance_inflation_factor(X.values, i)
              for i in range(X.shape[1])]

print(vif)
```

### VIF Interpretation

| VIF Value   | Interpretation           |
| ----------- | ------------------------ |
| VIF = 1     | No correlation           |
| 1 < VIF < 5 | Moderate correlation     |
| VIF > 5     | High correlation         |
| VIF > 10    | Severe multicollinearity |

---

# 🤖 Step 4: Building the Multiple Linear Regression Model

## Mathematical Model

[
Sales = β_0 + β_1(TV) + β_2(Radio) + β_3(SocialMedia) + ε
]

### Model Implementation

```python
X = df[['TV', 'Radio', 'Social Media']]
y = df['Sales']

X = sm.add_constant(X)

model = sm.OLS(y, X).fit()

print(model.summary())
```

---

# 📊 Step 5: Model Evaluation

The model is evaluated using:

* R-squared
* Adjusted R-squared
* F-statistic
* p-values
* Coefficient significance

### Important Metrics

#### R-squared

Measures the percentage of variance explained by the model.

#### Adjusted R-squared

Measures model performance while penalizing unnecessary predictors.

#### p-value

Determines whether a predictor significantly affects sales.

---

# 📉 Step 6: Residual Diagnostics

## 1. Residual vs Fitted Plot

Checks linearity and homoscedasticity.

```python
plt.scatter(model.fittedvalues,
            model.resid)

plt.axhline(y=0,
            color='red',
            linestyle='--')

plt.xlabel('Fitted Values')
plt.ylabel('Residuals')
plt.title('Residual vs Fitted Plot')
plt.show()
```

---

## 2. Normal Q-Q Plot

Checks whether residuals are normally distributed.

```python
sm.qqplot(model.resid,
          line='45')

plt.title('Normal Q-Q Plot')
plt.show()
```

---

## 3. Histogram of Residuals

```python
plt.hist(model.resid,
         bins=20)

plt.title('Distribution of Residuals')
plt.show()
```

---

# ✅ Assumption Validation Checklist

| Assumption           | Validation Method       |
| -------------------- | ----------------------- |
| Linearity            | Residual Plot           |
| Independence         | Durbin-Watson Statistic |
| Normality            | Q-Q Plot                |
| Homoscedasticity     | Residual Plot           |
| No Multicollinearity | VIF                     |

---

# 📖 Interpretation of Coefficients

Suppose the model produced:

| Variable     | Coefficient |
| ------------ | ----------- |
| TV           | 0.045       |
| Radio        | 0.188       |
| Social Media | 0.002       |

### Interpretation

* A ₦1 increase in TV advertising spending increases sales by **0.045 units**, holding other variables constant.
* A ₦1 increase in Radio advertising spending increases sales by **0.188 units**, holding other variables constant.
* A ₦1 increase in Social Media advertising spending increases sales by **0.002 units**, holding other variables constant.

---

# 💼 Business Insights

After analyzing the model:

### Recommendation 1

Increase investment in the marketing channel with the highest positive coefficient and statistically significant p-value.

### Recommendation 2

Reduce spending on channels with insignificant coefficients.

### Recommendation 3

Use the regression model to forecast future sales before allocating advertising budgets.

### Recommendation 4

Continuously monitor advertising performance and retrain the model with new data.

---

# 📌 Conclusion

This project demonstrates how Multiple Linear Regression can be used to:

* Quantify the impact of marketing expenditures.
* Understand relationships among multiple predictors.
* Validate statistical assumptions.
* Generate actionable business insights.
* Support data-driven decision-making in marketing strategy.

---

# 🚀 Future Improvements

* Add interaction terms.
* Include additional marketing channels.
* Compare with Ridge and Lasso Regression.
* Perform feature engineering.
* Deploy the model as a web application.



# 👨‍💻 Author

**Abdulmumin Inda Lawal**

Teacher | Data Science Enthusiast | Machine Learning Learner

---

# ⭐ If you found this project useful, kindly give it a star on GitHub.
