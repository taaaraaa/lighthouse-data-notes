## Reading a CSV file, but choosing only some columns
``` python

df = pd.read_csv('weight-height.csv', usecols = ['Height', 'Weight'])
```
## Reading a CSV file that are splitted by ; instead of ,
``` python

df = pd.read_csv('weight-height.csv', ,sep=';') 
```
