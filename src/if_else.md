# The IF . . . ELSE flow element

You use the IF . . . ELSE element to control the flow of your code based on the result of a predicate. You specify a statement or statement block that is executed if the predicate is TRUE, and optionally a statement or statement block that is executed if the predicate is FALSE.

```sql
IF YEAR(SYSDATETIME()) <> YEAR(DATEADD(day, 1, SYSDATETIME()))
  PRINT 'Today is the last day of the year.';
ELSE
  PRINT 'Today is not the last day of the year.';
```

---

```sql
IF YEAR(SYSDATETIME()) <> YEAR(DATEADD(day, 1, SYSDATETIME()))
  PRINT 'Today is the last day of the year.';
ELSE
  IF MONTH(SYSDATETIME()) <> MONTH(DATEADD(day, 1, SYSDATETIME()))
    PRINT 'Today is the last day of the month but not the last day of the year.';
  ELSE
    PRINT 'Today is not the last day of the month.';
```

