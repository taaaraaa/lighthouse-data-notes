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






