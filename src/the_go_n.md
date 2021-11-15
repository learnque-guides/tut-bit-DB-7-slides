# The GO n

The GO command is not really a T-SQL command; it’s actually a command used by SQL Server’s client tools, such as SSMS, to denote the end of a batch. This command supports an argument indicating how many times you want to execute the batch.

```sql
DROP TABLE IF EXISTS dbo.T1;
CREATE TABLE dbo.T1(col1 INT IDENTITY);
GO

INSERT INTO dbo.T1 DEFAULT VALUES;
GO 100

SELECT * FROM dbo.T1;
```