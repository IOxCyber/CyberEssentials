## Prevention of SQLi:
1. `Use parameterized queries (prepared statements)` - Treat User Input as Data, not the executable codes.
- When using parameterized queries, SQL query is defined with placeholders. (SQLite3, JDBC, PDO in PHP)
- then binds parameters, the user input is treated purely as data.
- The database `server knows to insert these values only into the designated placeholders`, without executing them as part of the SQL code.

2. `Implement strong input validation and sanitization` - Apply strict input validation to allow only expected characters or patterns on Server/Client side.
- 


3. `Apply the principle of least privilege (PoLP)` - Limit database user privileges

4. `Keep software and frameworks up to date`

5. `Perform security testing and code reviews`
