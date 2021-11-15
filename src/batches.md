# Batches

* A batch is one or more T-SQL statements sent by a client application to SQL Server for execution as a single unit.

* SQL Server utilities such as SQL Server Management Studio (SSMS), SQLCMD, and OSQL provide a client tool command called GO that signals the end of a batch.

* A batch is a set of commands that are parsed and executed as a unit. If the parsing is successful, SQL Server then attempts to execute the batch. In the event of a syntax error in the batch, the whole batch is not submitted to SQL Server for execution.

```sql
-- Valid batch
PRINT 'First batch';
USE lessons;
GO
-- Invalid batch
PRINT 'Second batch';
SELECT custid FROM Sales.Customers;
SELECT orderid FOM Sales.Orders;
GO
-- Valid batch
PRINT 'Third batch';
SELECT empid FROM HR.Employees;
```