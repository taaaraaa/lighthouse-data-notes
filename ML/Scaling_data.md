## MinMaxScaler (data between 0 and 1)
For each value in a feature, MinMaxScaler subtracts the minimum value in the feature and then divides by the range. The range is the difference between the original maximum and original minimum. MinMaxScaler preserves the shape of the original distribution.
### Coding
``` python
from sklearn.preprocessing import MinMaxScaler
import pandas as pd

# create example dataframe
df = pd.DataFrame({'col1': [1, 2, 3, 4, 5], 'col2': [100, 200, 300, 400, 500]})

# create scaler object
scaler = MinMaxScaler()

# fit and transform the dataframe
scaled_df = pd.DataFrame(scaler.fit_transform(df), columns=df.columns)

print(scaled_df)
```
In this example, the MinMaxScaler scales each column in the dataframe to a range between 0 and 1. The fit_transform() method fits the scaler to the data and then applies the scaling transformation. The resulting scaled dataframe is stored in scaled_df.

### output
```
   col1  col2
0   0.0   0.0
1   0.25  0.25
2   0.5   0.5
3   0.75  0.75
4   1.0   1.0
```


## StandardScaler (mean 0 and variance 1)
StandardScaler() will normalize the features i.e. each column of X, INDIVIDUALLY, so that each column/feature/variable will have μ = 0 and σ = 1.

!['the math'](../data/standardscaler.png)

### Coding
``` python
from sklearn.preprocessing import StandardScaler
import pandas as pd

# create example dataframe
df = pd.DataFrame({'col1': [1, 2, 3, 4, 5], 'col2': [100, 200, 300, 400, 500]})

# create scaler object
scaler = StandardScaler()

# fit and transform the dataframe
scaled_df = pd.DataFrame(scaler.fit_transform(df), columns=df.columns)

print(scaled_df)

```
### output
```
       col1      col2
0 -1.264911 -1.264911
1 -0.632456 -0.632456
2  0.000000  0.000000
3  0.632456  0.632456
4  1.264911  1.264911
```

In this example, the StandardScaler standardizes each column in the dataframe to have mean 0 and variance 1. The fit_transform() method fits the scaler to the data and then applies the standardization transformation. The resulting standardized dataframe is stored in scaled_df.

## MinMaxscaler vs. StandardScaler
The MinMaxscaler is a type of scaler that scales the minimum and maximum values to be 0 and 1 respectively. While the StandardScaler scales all values between min and max so that they fall within a range from min to max.Jul 27, 2020
