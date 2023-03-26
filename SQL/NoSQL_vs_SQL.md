# NoSQL vs. SQL

The main motivation behind NoSQL is the growing amount of data. Traditional relational databases depend on something called ETL or Extract, Transform, and Load. It is a process that extracts data from the source, for example, a POS (point-of-sales) terminal where we pay with our card, transforms it into tables that are part of a pre-defined schema, and load that into a database.

Nowadays, in some cases, there are so much data that it is impossible to do ETL before storing them. That's why NoSQL databases have boomed in the last couple of years. They can store data in a raw form, eliminating the need for preprocessing, and allow companies to store huge volumes of them.

## SQL Database Systems
Here are some of the most popular SQL database systems:

### MySQL
- Free and open-source 
- An extremely established database with a huge community, extensive testing, and lots of stability
- Supports all major platforms
- Replication and sharding are available
- Covers a wide range of use cases 

### Oracle
- Commercial database with frequent updates, professional management, and excellent customer support
- Procedural Language/SQL or PL/SQL is the SQL dialect used 
- One of the most expensive database solutions 
W- orks with huge databases 
- Simple upgrades
- Transaction control
- Compatible with all operating systems
### Microsoft SQL Server
- A commercial database developed and managed by Microsoft
Transact SQL, or T-SQL, is the SQL dialect used 
- Only works with Windows and Linux 
- User-friendly
- Difficult to make adjustments mid-process when finding errors
- Excellent documentation
- Works well for small-to-medium-sized organizations that want a commercial database solution without the cost of Oracle
### PostgreSQL
- Object-oriented database management system, meaning it’s a hybrid SQL/NoSQL database solution 
- Free and open-source 
- Compatibility with a wide range of operating systems 
- Active community and many third-party service providers 
- High ACID compliance 
- Uses pure SQL 
- Works best for use cases where data doesn’t support a relational model.
- It also works well for extra-large databases and when running complicated queries

## NoSQL Database Systems
Here are a couple of the most popular NoSQL database systems: 

### MongoDB
By far the most popular NoSQL database, and for good reason
- Free to use 
- Dynamic schema 
- Horizontally scalable 
- Excellent performance with simple queries
- Add new columns and fields without impacting your existing rows or application - performance
- Works best for companies going through rapid growth stages or those with a lot of unstructured data

Lesser-known alternatives to MongoDB include Apache Cassandra, Google Cloud BigTable, and Apache HBase

### Cassandra
- Handles large amounts of data across commodity servers
- High availability with no point of failure
- Follows peer-to-peer architecture
- Scalable 
- Open-source