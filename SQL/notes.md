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