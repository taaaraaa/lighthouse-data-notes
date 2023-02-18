## 1. Methods: From Data
Although attributes are about matadata, Methods are about functionalities and behaviour of the object.
Different libraries have different methods. Methods manipulate object, thus each object have its own methods. For example, methods used for Series cannot be used for DataFrames and vise versa.
``` Python
x.sum()
x.max()
x.min()
x.idxmax()
x.idxmin()
```

Methods and functions are very similar. They both make specific opertions and return an output
## 2. Parameters
## 3. Arguments
## 4 Attributes: About Data
Information about the metadata
Attributes are Passive while Methods are Active

x.dtype

x.size

x.name

x.index

## 5. Index Values
- Label based indexing
- Position based indexing = Axis Labels ~ a non numeric index
``` Python
# to know what are the indexes
x.index
# to get the value of a specific position-based index 
x[0]
# to get the value of a specific label-based index - example. In this examle we can also use the previous method! (suppose Product A is the first data in the Series)
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