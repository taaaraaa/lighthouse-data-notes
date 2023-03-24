## Importing a CSV file
``` python
airbnb_data = pd.read_csv("data/listings_austin.csv")
```
## Reading a CSV file, but choosing only some columns
``` python
df = pd.read_csv('weight-height.csv', usecols = ['Height', 'Weight'])
```
## Reading a CSV file that are splitted by `;` instead of `,`
``` python
df = pd.read_csv('weight-height.csv', ,sep=';') 
```
## Importing a parquet file
``` python
pip install pandas pyarrow fastparquet

df = pd.read_parquet('./tables/flights_sample_large.parquet')
```

## Exmporting as a CSV file
``` python
df.to_csv('my_data.csv', index=False)
```
## Exmporting as a parquet file
``` python
df.to_parquet('my_data.parquet', index=False)
```


## Drop a col
``` python
# drop the 'City' column
df = df.drop('col_name', axis=1)

df = df.drop(columns=['col_1', 'col_2'])
print(df)
```
## Drop the Rows with NaN Values in Pandas DataFrame
``` python
df = df.dropna()
```
## Add a col
``` python
#adding empty col
df["D"] = np.nan
```
``` python
#adding values to the empty col

for i in range(1):
    df.loc[i,['D','E']]=['apple','banana']
```
## Rename a col
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

## Create combo chart
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


## reorder cols
df = df[['mean', '0', '1', '2', '3']]

## Filter based on col value
```python
df[df['cancelled']==0]
```
``` python
# select rows containing 'bbi'
df.filter(like='bbi', axis=0)
```
``` python
#filter based on values of two columns
filtered=X2[(X2['tail_num'] == 'N569JB') & (X2['fl_date'] == '2018-01-01')]
```
## Select sample random rows
``` python
# To get 3 random rows
# each time it gives 3 different rows
 
# df.sample(n = 3) or
df.sample(3)
```

``` python
# Fraction of rows
 
# here you get .50 % of the rows
df.sample(frac = 0.5)
```

## Reset Index
``` python
# (drop=True) will remove previous index col
df.reset_index(drop=True)
```

## Replace space with dash

``` python
X_weather_2['origin_city_name'] = X_weather_2['origin_city_name'].str.replace(' ', '-')
```
