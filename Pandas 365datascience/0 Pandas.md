These notes are from [365datascience](https://learn.365datascience.com/courses/preview/data-cleaning-preprocessing-pandas/)


## 1. Methods: From Data
Although attributes are about matadata, Methods are about functionalities and behaviour of the object.
Different libraries have different methods. Methods manipulate object, thus each object have its own methods. For example, methods used for Series cannot be used for DataFrames and vise versa.
``` Python
x.sum()
x.max()
x.min()
x.idxmax()
x.idxmin()
x.head()
x.tail()
```

Methods and functions are very similar. They both make specific opertions and return an output
## 2. Parameters
Parameters are associated with certain pandas method to modify the reuslts. It is a good practice to write the parameters with right acronym and right order!

We can be specific about Method outputs. It is where parameter comes!
``` Python
x.head(10)
x.tail(14)
```
## 3. Arguments
Artument is the number we give to Parameter. In the previous example, 10 and 14 are arguments.
### Pandas **Methods** have **Parameters** you can supply with **Arguments** to modify the perfomance of the given method!

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
It is a great reference for different Pandas Methods, Parameteres and so on! Click [Here](https://pandas.pydata.org/docs/user_guide/index.html) to access it!

## 7. Data Types in Pandas:
### 7-1 Series

    Similar to arrays in Numpy. To create one we can do by the following:
``` Python
# index is optional
y=['cat','dog','horse']
x=pd.Series(y,index=['animal 1','animal 2', 'animal 3'])
```
### 7-2 DataFrame
- It is the mostly used pandas object.
- It is a collection of multipe Series
- Series are one-dimensional, containing values along a single axis(rows)
- DataFrame contains values not only in rows, bult also in columns. So it is the closest python analogue to a standard two-dimentional data set or as a spreadsheet
- DataFrame= Two-dimentional data structure= Two-dimentional NumPy array= 2-D Matrix
- While Series are single column data, DataFrame are Multi-column data
- Every column represent a different data type, so each column can have its own data type, but each column should contain the same data type!

Data Frames has the following parameters:
- data
- column
- index

![DataFrame Vs Series](/pics/DataFrame-VS-Series.png)

![DataFrame Vs Series](/pics/DataFrame-VS-Series-2.png)

![DataFrame Vs Series](/pics/DataFrame-VS-Series-3.png)

