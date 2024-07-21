 # General order of execution for a SQL query:
```
FROM: Identify the tables involved in the query.
WHERE: Filter the rows based on the specified conditions.
GROUP BY: Group the filtered rows.
HAVING: Filter groups based on a condition.
SELECT: Select the columns or expressions to return.
ORDER BY: Order the result set.
LIMIT: Limit the number of rows returned.
```

> Execution Order: FROM → WHERE → SELECT → IF → WAITFOR DELAY


