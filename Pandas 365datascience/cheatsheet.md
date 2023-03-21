## drop a col
``` python

# create a sample dataframe
df = pd.DataFrame({'Name': ['John', 'Emily', 'Tom', 'Anna'],
                   'Age': [28, 35, 42, 23],
                   'City': ['New York', 'Chicago', 'Los Angeles', 'Houston']})

# drop the 'City' column
df = df.drop('City', axis=1)

print(df)
```
## rename a col
df = df.rename(columns={'City': 'Location'})

## Find the corel btw two columns

``` python
# create a sample dataframe
df = pd.DataFrame({'Age': [28, 35, 42, 23, 46],
                   'Salary': [50000, 65000, 80000, 45000, 90000],
                   'Experience': [3, 6, 8, 2, 10]})

# calculate the correlation between 'Age' and 'Salary'
correlation = df['Age'].corr(df['Salary'])

print(correlation)
```

## Plot the corel
In the above example df:


``` python
import pandas as pd
import matplotlib.pyplot as plt

# plot a scatter plot with 'Age' as x and 'Salary' as y
plt.scatter(df['Age'], df['Salary'])

# add a title and axis labels
plt.title('Correlation between Age and Salary')
plt.xlabel('Age')
plt.ylabel('Salary')

# add the correlation value as text to the plot
plt.text(df['Age'].max() * 0.8, df['Salary'].max() * 0.9,
         'Correlation = {:.2f}'.format(correlation),
         fontsize=12, color='blue')
```

## Mergin two tables

join_checking_credit = pd.merge(checking_tran,credit_tran, on='cust_id',how='outer')
join_checking_credit