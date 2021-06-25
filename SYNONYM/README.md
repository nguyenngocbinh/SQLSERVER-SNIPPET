# SYNONYM

[SYNONYM] (https://www.sqlservertutorial.net/sql-server-basics/sql-server-synonym/)

Creating a synonym for a table in another database

First, create a new database named test and set the current database to test:

```
CREATE DATABASE test;
GO

USE test;
GO
```


Next, create a new schema named purchasing inside the test database:

```
CREATE SCHEMA purchasing;
GO
```


Then, create a new table in the purchasing schema of the test database:

```
CREATE TABLE test.purchasing.suppliers
(
    supplier_id   INT
    PRIMARY KEY IDENTITY, 
    supplier_name NVARCHAR(100) NOT NULL
);
```

After that, from the BikeStores database, create a synonym for the purchasing.suppliers table in the test database:

```
USE BikeStores;
GO

CREATE SYNONYM suppliers 
FOR test.purchasing.suppliers;

```

Finally, from the BikeStores database, refer to the test.purchasing.suppliers table using the suppliers synonym:

```
SELECT * FROM suppliers;
```

Removing a synonym

```
DROP SYNONYM IF EXISTS orders;
```
