# Storedprocedure

## DateTime SQL

http://stackoverflow.com/questions/10061665/type-datetime-for-input-parameter-in-procedure

Type datetime for input parameter in procedure

```sql
declare @a datetime
declare @b datetime

set @a = '2012-04-06T12:23:45' -- 6th of April, 2012
set @b = '2012-08-06T21:10:12' -- 6th of August, 2012

exec LogProcedure 'AccountLog', N'test', @a, @b


IF @DateFirst <> '' and @DateLast <> ''
SET @FinalSQL = @FinalSQL + ' OR CONVERT(Date, DateLog) >= ''' +
CONVERT(VARCHAR(50), @DateFirst, 126) + -- convert @DateFirst to string for concatenation!
''' AND CONVERT(Date, DateLog) <=''' + -- you need closing quotes after @DateFirst!
CONVERT(VARCHAR(50), @DateLast, 126) + '''' -- convert @DateLast to string and also: closing tags after that missing!
```

Stored Procedure with Optional DateTime Parameters in SQL Server

```sql
CREATE PROCEDURE [dbo].[prSearchEmployees]
(
@Id INT = NULL
,@FullName VARCHAR(20) = NULL
,@Age INT = NULL
,@StartDate DATETIME = NULL
,@EndDate DATETIME = NULL
)
AS
BEGIN

DECLARE @SDate DATETIME
DECLARE @EDate DATETIME

SET @SDate = ISNULL(@StartDate, GETDATE())
SET @EDate = ISNULL(@EndDate, GETDATE())


SELECT * FROM Employee
WHERE Id = ISNULL(@Id, Id)
AND FullName LIKE ISNULL(@FullName + '%', FullName)
AND Age = ISNULL(@Age, Age)
AND Date BETWEEN @SDate AND @EDate
```
