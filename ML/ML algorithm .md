# Linear Regression
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

## Perform Regression in Python using Statsmodels

``` Python
import pandas as pd
import statsmodels.api as sm

data = {'year': [2017,2017,2017,2017,2017,2017,2017,2017,2017,2017,2017,2017,2016,2016,2016,2016,2016,2016,2016,2016,2016,2016,2016,2016],
        'month': [12,11,10,9,8,7,6,5,4,3,2,1,12,11,10,9,8,7,6,5,4,3,2,1],
        'interest_rate': [2.75,2.5,2.5,2.5,2.5,2.5,2.5,2.25,2.25,2.25,2,2,2,1.75,1.75,1.75,1.75,1.75,1.75,1.75,1.75,1.75,1.75,1.75],
        'unemployment_rate': [5.3,5.3,5.3,5.3,5.4,5.6,5.5,5.5,5.5,5.6,5.7,5.9,6,5.9,5.8,6.1,6.2,6.1,6.1,6.1,5.9,6.2,6.2,6.1],
        'index_price': [1464,1394,1357,1293,1256,1254,1234,1195,1159,1167,1130,1075,1047,965,943,958,971,949,884,866,876,822,704,719]        
        }

df = pd.DataFrame(data) 

x = df[['interest_rate','unemployment_rate']]
y = df['index_price']

x = sm.add_constant(x)

model = sm.OLS(y, x).fit()
predictions = model.predict(x) 

print_model = model.summary()
print(print_model)
```
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





