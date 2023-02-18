## 1. Methods
## 2. Parameters
## 3. Arguments
## 4 Attributes
x.dtype

x.size

x.name
## 5. Index Values
- Label based indexing
- Position based indexing
``` Python
# to know what are the indexes
x.index
# to get the value of a specific position-based index 
x[0]
# to get the value of a specific label based index - example. In this examle we can also use the previous method! (suppose Product A is the first data in the Series)
x['product A']=x[0]
```
## 6. Pandas Documentation

## 7. Data Types in Pandas:
- Series

    Similar to arrays in Numpy. To create one we can do by the following:
``` Python
# index is optional
y=['cat','dog','horse']
x=pd.Series(y,index=['animal 1','animal 2', 'animal 3'])
```
- DataFrame