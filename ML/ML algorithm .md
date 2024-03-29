# Linear Regression
There are three types: 
1. Simple Linear Regression (one feature )
> y=b0+b1x1

        b0=intercept/constant/bias
        b1=coefficient/slope/weight

2. Multiple Linear Regression (several features)
> y = b0 +b1x1+b2x2+...+bnxn

![matrix representation](../data/matrix-representation.png "matrix representation in multiple linear regression")

3. Polynomial Regression (one feature )
> y = b0+ b1x1 + b1x1^2 + ... + bnx1^n


We calculate by doing the following:
- Use least-squares to fit a line to the data
- Calculate R^2
- Calculate a p-value for R^2

:memo: **Terminology Alert:** The distance from a line to a data point is called a "**residual**".

:memo: **Terminology Alert:** Sum of squares around the mean of dataset(we calculate it only for the dependent variable of the  dataset or y) "**SS(mean)**" or mathematically it is:
> SS(mean)=(data-mean)^2

> Var(mean) = SS(mean)/n 

> Var(fit)=(data-line)^2/n=SS(fit)/n

> R^2=(Var(mean)-Var(fit)) / Var(mean)

R^2 can be calculated as below too:

> R^2= (SS(mean)-SS(fit)) / SS(mean)

There is a R^2 reduction in variance when we take the independent variable (such as mouse weight) into account! In other words, we can say that mouse weight explains R^2 % of the variation in mouse size!

:bulb: **Tip:** When we add another dependent variable to our linear regression model, the R-squared increases, which tempts you to add more. Some of the independent variables will be statistically significant.

## Perform Regression in Python
you can [follow this notebook](https://github.com/taaaraaa/lighthouse-data-notes/blob/main/ML/Linear%20Regression%20in%20ML.ipynb)

We can use either  Statsmodels or Skilearn, below is the output example for *Statsmodels**


``` python
                            OLS Regression Results                            
==============================================================================
Dep. Variable:            index_price   R-squared:                       0.898
Model:                            OLS   Adj. R-squared:                  0.888
Method:                 Least Squares   F-statistic:                     92.07
Date:                Sat, 30 Jul 2022   Prob (F-statistic):           4.04e-11
Time:                        13:24:29   Log-Likelihood:                -134.61
No. Observations:                  24   AIC:                             275.2
Df Residuals:                      21   BIC:                             278.8
Df Model:                           2                                         
Covariance Type:            nonrobust                                         
=====================================================================================
                        coef    std err          t      P>|t|      [0.025      0.975]
-------------------------------------------------------------------------------------
const              1798.4040    899.248      2.000      0.059     -71.685    3668.493
interest_rate       345.5401    111.367      3.103      0.005     113.940     577.140
unemployment_rate  -250.1466    117.950     -2.121      0.046    -495.437      -4.856
==============================================================================
Omnibus:                        2.691   Durbin-Watson:                   0.530
Prob(Omnibus):                  0.260   Jarque-Bera (JB):                1.551
Skew:                          -0.612   Prob(JB):                        0.461
Kurtosis:                       3.226   Cond. No.                         394.
==============================================================================
```
### Interpreting the Regression Results
several important components within the results:

1. **Adjusted. R-squared** reflects the fit of the model. R-squared values range from 0 to 1, where a higher value generally indicates a better fit, assuming certain conditions are met.

2. **const coefficient** is your Y-intercept. It means that if both the interest_rate and unemployment_rate coefficients are zero, then the expected output (i.e., the Y) would be equal to the const coefficient.

3. **interest_rate coefficient** represents the change in the output Y due to a change of one unit in the interest rate (everything else held constant)

4. **unemployment_rate coefficient** represents the change in the output Y due to a change of one unit in the unemployment rate (everything else held constant)
5. **std err** reflects the level of accuracy of the coefficients. The lower it is, the higher is the level of accuracy

6. **P >|t|** is your p-value. A p-value of less than 0.05 is considered to be statistically significant

7. **Confidence Interval** represents the range in which our coefficients are likely to fall (with a likelihood of 95%)


# Polynomial Linear Regression

> y = b0+ b1x1 + b1x1^2 + ... + bnx1^n


:bulb: **Tip:** The main difference between multinomial and polynomial regression is that we still use only one feature but with many transformations.

:bulb: **Tip:** IT is still called linear, because it is calculating coefficients (b)

# SVM
The Support Vector Machine (SVM) is a supervised machine learning algorithm that can be employed for both classification and regression purposes. The SVM is more commonly used in classification problems and as such, this is what we will focus on for now.

# Logistic Regression
It is the most frequently applied classification method.

The types of Logistic Regression:

1. Binary Logistic Regression – the categorical response has only two possible outcomes. Example: Spam or Not.
2. Multinomial Logistic Regression – three or more categories without ordering. Example: Predicting which food is more preferred: Veg/Non-Veg/Vegan.
Ordinal Logistic Regression– three or more categories with ordering. Example: Movie rating from 1 to 5.
------------------------
## What is a Decision Tree?


Decision Trees are a non-parametric supervised learning method used for classification and regression. Decision trees learn from data to approximate a curve with a set of if-then-else decision rules. The decision tree builds classification or regression models in the form of a tree structure. It breaks down a dataset into smaller and smaller subsets while, at the same time, an associated decision tree is incrementally developed. The final result is a tree with decision nodes and leaf nodes.

---------------
## Random Forest
Random forest is a flexible, easy-to-use machine learning algorithm that produces, even without hyper-parameter tuning, a great result most of the time. It is also one of the most frequently used algorithms, because of its simplicity and diversity (it can be used for both classification and regression tasks).

------------
## XGBoost

XGBoost is a special type of a gradient boosting algorithm. It is very popular in practice because of its speed and accuracy. It has an impressive record of winning Kaggle competitions and it can be even more effective than Deep Neural Networks. When we have to deal with the classic tabular data trade-off between training time and accuracy we will always be favoring XGBoost.

There's a big chance that this is the algorithm we will end up using for many predictive modeling use-cases. 

-----------
## What is Ensemble Learning?

Ensemble methods use multiple learning algorithms to obtain better predictive performance than could be obtained from any of the constituent learning algorithms alone.