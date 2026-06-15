# Multiple Linear Regression – Marketing Analysis

##                                            Project Overview
This project analyzes the impact of different marketing channels (TV, Influencer Marketing, and Social Media) on Sales using Multiple Linear Regression (OLS) in Python. The goal is to identify which marketing channels drive sales most effectively and provide data-driven recommendations for budget allocation.

##                                               Objectives
- Build a Multiple Linear Regression model
- Evaluate relationships between marketing channels and Sales
- Check for multicollinearity using VIF
- Interpret regression coefficients
- Provide business insights for marketing strategy

##                                               Dataset Features
- TV: Budget spent on TV advertising
- Influencer: Influencer marketing spend
- Social Media: Social media advertising spend
- Sales: Revenue generated (target variable)

##                                               Tools & Libraries
- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Statsmodels
-sklearn

## Methodology

###                                                 Data Exploration
- Checked missing values
- Descriptive statistics
- Correlation analysis

###                                             Multicollinearity Check
- Variance Inflation Factor (VIF)
- Result: No multicollinearity detected (VIF ≈ 1 for all predictors)

###                                                 Model Building
- Multiple Linear Regression using OLS (statsmodels)

###                                                 Model Evaluation
- Adjusted R-squared
- p-values for statistical significance
- Residual diagnostics

## Key Findings

- Social Media has the strongest positive effect on Sales
- Influencer marketing has a mild positive effect
- TV advertising shows a negative relationship with Sales
- No multicollinearity issues detected

##                                              Business Recommendations

- Increase investment in Social Media marketing
- Maintain Influencer marketing as a supporting strategy
- Re-evaluate or optimize TV advertising strategy due to negative impact
- Use data-driven budget allocation for improved ROI

## How to Run This Project

```bash
pip install -r requirements.txt

open notebook:
Marketing Sales.ipynb

## Author
Abdulmumin Lawal