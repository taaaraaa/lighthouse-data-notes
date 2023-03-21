## drop a col
``` python

# create a sample dataframe
df = pd.DataFrame({'Name': ['John', 'Emily', 'Tom', 'Anna'],
                   'Age': [28, 35, 42, 23],
                   'City': ['New York', 'Chicago', 'Los Angeles', 'Houston']})

# drop the 'City' column
df = df.drop('City', axis=1)

df = df.drop(columns=['Age', 'City'])
print(df)
```
## rename a col
``` python
df = df.rename(columns={'City': 'Location', 'aaa':'bbb'})
```

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

## Merging two tables

``` python
join_checking_credit = pd.merge(checking_tran,credit_tran, on='cust_id',how='outer')

```
## Select the last two chars in a col
``` python

States_air_traffic['origin_city_name'] = States_air_traffic['origin_city_name'].map(lambda x: str(x)[-2:])

```

## Groupby
``` python
a_avg = a.groupby('month').mean().reset_index()
```
## Histogram

fig1 = plt.hist(X['arr_delay_log'])
plt.show()

## create combo chart
``` python
import pandas as pd
import matplotlib.pyplot as plt

left_2013 = pd.DataFrame(
    {'month': ['jan', 'feb', 'mar', 'apr', 'may', 'jun', 'jul', 'aug', 'sep',
               'oct', 'nov', 'dec'],
     '2013_val': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 9, 6]})

right_2014 = pd.DataFrame({'month': ['jan', 'feb'], '2014_val': [4, 5]})

right_2014_target = pd.DataFrame(
    {'month': ['jan', 'feb', 'mar', 'apr', 'may', 'jun', 'jul', 'aug', 'sep',
               'oct', 'nov', 'dec'],
     '2014_target_val': [2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]})

df_13_14 = pd.merge(left_2013, right_2014, how='outer')
df_13_14_target = pd.merge(df_13_14, right_2014_target, how='outer')

ax = df_13_14_target[['month', '2014_target_val']].plot(
    x='month', linestyle='-', marker='o')
df_13_14_target[['month', '2013_val', '2014_val']].plot(x='month', kind='bar',
                                                        ax=ax)

plt.show()
```