# Server-Side Vulnerability

## SQLi: `manipulates a web application's database queries by injecting malicious SQL code.` [cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)
- a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.
- Most SQL injection vulnerabilities arise within the WHERE clause of a SELECT query. 
- can leads to DOS attack, steal info(pwd/cc info)


## How to detect: Test in the search field, login form, or any other form & look for errors/outputs
- <img width="500" alt="image" src="https://github.com/cybersome/CyberEssentials/assets/40174034/46b66669-863d-4796-937a-a11da9bbbd84">
> single-quote(') character is used to properly format the injected payload as a string literal within the original query.

## Injection Examples:
### A. `Retrieving hidden data`, where you can modify a SQL query to return additional results.
1. Testing for boolean-based attacks:
- `'OR 1=1 --` - This payload appends an OR condition that always evaluates to true, commenting out the remaining portion of the original query.
- `'OR 'x'='x` - This payload compares a string with itself, resulting in a true condition.

2. Testing for time-based attacks:
- `'OR SLEEP(5) --` - This payload tries to induce a delay of 5 seconds in the SQL query execution by using the SLEEP function. If the website is vulnerable, it will take longer to respond.
- `'OR BENCHMARK(10000000,SHA1(1)) --` - This payload attempts to measure the time taken to execute the SHA1 function a large number of times, causing a significant delay if the SQL injection is successful.

3. Testing for error-based attacks:
- `'OR 1=1; DROP TABLE users; --` - This payload combines a valid condition (1=1) with a malicious action (DROP TABLE users), potentially causing an error and deleting the "users" table.
-  `'OR 1=1 UNION ALL SELECT NULL, CONCAT(username,':', password) FROM users --` - This payload attempts to perform a UNION-based SQL injection to retrieve the usernames and passwords from the "users" table.


### B. `Subverting/interfering with application logic`, change a query to interfere with the application's logic.
- testing on a login page involves attempting to subvert the application logic and bypass the authentication mechanism

### C. `UNION attacks, retrieve data from different database tables.`
- a technique used to combine the result sets of two or more SELECT statements in a SQL query
- eg. SELECT * FROM users WHERE username = 'input_username' AND password = 'input_password';
- insert it in `username` ' UNION SELECT null, table_name FROM information_schema.tables -- (-- to comment out rest of the original query)
- `SELECT * FROM users WHERE username = '' UNION SELECT null, table_name FROM information_schema.tables --' AND password = 'input_password';`


### D. `Blind SQL injection, where the results of a query you can't see in the application's responses.`
- Similar to other SQL injection attacks. However, the attacker doesn't see the direct results of their injected queries.
- Trial and error, the attacker continues to extract data by asking a series of true or false questions, gradually revealing sensitive information such as database structure, table names, or even specific data records.

## Blind SQL Injection Testing

### Test Case 1: Boolean-Based Blind SQL Injection
**Test Objective**: To check if the application is vulnerable to boolean-based blind SQL injection.

**Test Steps**:
1. Enter a legitimate username and password in the login form.
2. In the username field, append a single quote (`'`) and `AND 1=1--` to inject a condition that is always true.
3. Observe the application's response.

**Expected Outcome**: The login should be successful, indicating a vulnerability to boolean-based blind SQL injection.

### Test Case 2: Time-Based Blind SQL Injection
**Test Objective**: To check if the application is vulnerable to time-based blind SQL injection.

**Test Steps**:
1. Enter a legitimate username and password in the login form.
2. In the username field, append a single quote (`'`) and `AND SLEEP(5)--` to introduce a delay of 5 seconds in the query execution.
3. Observe the application's response.

**Expected Outcome**: The login process should exhibit a noticeable delay, indicating a vulnerability to time-based blind SQL injection.

### Test Case 3: Error-Based Blind SQL Injection
**Test Objective**: To check if the application is vulnerable to error-based blind SQL injection.

**Test Steps**:
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



## Prevention of SQLi:
1. `Use parameterized queries (prepared statements)` - Treat User Input as Data, not the executable codes.
2. `Implement strong input validation and sanitization` - Apply strict input validation to allow only expected characters or patterns on Server/Client side.
3. `Apply the principle of least privilege (PoLP)` - Limit database user privileges
4. `Keep software and frameworks up to date`
5. `Perform security testing and code reviews`

