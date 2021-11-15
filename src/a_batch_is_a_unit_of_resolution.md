# A batch as a unit of resolution

* A batch is a unit of resolution (also known as binding). This means that checking the existence of objects and columns happens at the batch level. 
* When you apply schema changes to an object and try to manipulate the object data in the same batch, SQL Server might not be aware of the schema changes.

```sql
DROP TABLE IF EXISTS dbo.T1;
CREATE TABLE dbo.T1(col1 INT);

ALTER TABLE dbo.T1 ADD col2 INT;
SELECT col1, col2 FROM dbo.T1;
```

* Best practice you can follow to avoid such problems is to separate data-definition language (DDL) and Data-Manipulation Language (DML) statements into different batches.

```sql
DROP TABLE IF EXISTS dbo.T1;
CREATE TABLE dbo.T1(col1 INT);
ALTER TABLE dbo.T1 ADD col2 INT;
GO
SELECT col1, col2 FROM dbo.T1;
```