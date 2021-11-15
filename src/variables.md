# Variables

* You use variables to temporarily store data values for later use in the same batch in which they were declared.
* A batch is one T-SQL statement or more sent to Microsoft SQL Server for execution as a single unit.

Use a DECLARE statement to declare one or more variables, and use a SET statement to assign a value to a single variable. 

```sql
DECLARE @i AS INT;
SET @i = 10;
GO
```

Another example that demonstrate variable visibility between different batches:

```sql
DECLARE @i AS INT;
GO -- One batch
-- Throw error. Visibility is one batch.
SET @i = 10;
GO -- Second one
```

You can declare and initialize a variable in the same statement, like this:

```sql
DECLARE @i AS INT = 10;
```

When you assign a value to a scalar variable, the value must be the result of a scalar expression. The expression can be a scalar subquery.

```sql
DECLARE @empname AS NVARCHAR(128);

SET @empname = (SELECT firstname + N' ' + lastname
                FROM HR.Employees
                WHERE empid = 3);

SELECT @empname AS empname;
```