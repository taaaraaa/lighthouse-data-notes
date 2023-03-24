 # import *.csv file into the PostgreSQL database 

1. Create a table
    - Open the Database
    - Right click on the table object on the left hand panel
    - Click create a table (give it a name and add columns specifying data types)

    OR
    - Open Query tool
    - Write a code to create a table such as below as an example:

    ``` SQL
    CREATE TABLE persons (
        id SERIAL,
        first_name VARCHAR,
        last_name VARCHAR,
        dob DATE,
        email VARCHAR,
        PRIMARY KEY (id)
    )
    ```

2. Import Data

    Right click on the table name on the left-hand panel and click import data

3. Check your data, for example:

 ``` SQL
SELECT * FROM persons;
```

## How to select a random 1000 rows of a table
select * from table where random() < 0.01 limit 1000;

## get the number of rows, columns, and file size in pgAdmin 4
``` sql
SELECT relname, reltuples, relpages * 8 / 1024 AS "Size (MB)", relkind 
FROM pg_class 
WHERE relname = 'table_name';
```
## number of unique values of a col

``` sql
SELECT COUNT(DISTINCT branded_code_share) FROM flights;
```
