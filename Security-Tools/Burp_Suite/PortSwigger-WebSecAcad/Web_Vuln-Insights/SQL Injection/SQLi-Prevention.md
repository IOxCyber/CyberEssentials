# Prevention of SQLi:

## 1. `Use parameterized queries (prepared statements)` - Treat User Input as Data, not the executable codes.
- When using parameterized queries, SQL query is defined with placeholders. (SQLite3, JDBC, PDO in PHP)
- These `parameterized queries are also know as "prepared statements"`

## How Parameterized Queries Work:
```
When using a PreparedStatement, the SQL query is sent to the database with placeholders (parameters).
The user inputs are then bound to these placeholders using methods like setString. Here’s what happens behind the scenes:

Precompilation: The SQL query with placeholders is precompiled by the database.
Parameter Binding: The user input is bound to the placeholders. The database driver ensures that the input is treated as a literal value by escaping any special characters.
Execution: The database executes the query with the safely bound parameters.
```

## Example 1:
- Injection: `userInput: userInput'; DROP TABLE users; --`

```
# Vulnerable Code:

String userInput = "userInput'; DROP TABLE users; --";
String query = "SELECT * FROM users WHERE name = '" + userInput + "'";
Statement statement = connection.createStatement();
ResultSet resultSet = statement.executeQuery(query);

Resulting Query: SELECT * FROM users WHERE name = 'userInput'; DROP TABLE users; --'   # This query will drop the users table.
```

## Example 2:
```
# Secure Code:

String userInput = "userInput'; DROP TABLE users; --";
PreparedStatement statement = connection.prepareStatement("SELECT * FROM users WHERE name = ?");
statement.setString(1, userInput);
ResultSet resultSet = statement.executeQuery();

The input is treated as a single string value, not as part of the SQL command.
SELECT * FROM users WHERE name = 'userInput''; DROP TABLE users; --'     The special characters in the input are escaped, and the database treats it as a literal string.
```

> With Parameterized, the special characters in the input are escaped, and the database treats it as a literal string.


## 2. `Implement strong input validation and sanitization` - Apply strict input validation to allow only expected characters or patterns on Server/Client side.
- 


## 3. `Apply the principle of least privilege (PoLP)` - Limit database user privileges

## 4. `Keep software and frameworks up to date`

## 5. `Perform security testing and code reviews`
