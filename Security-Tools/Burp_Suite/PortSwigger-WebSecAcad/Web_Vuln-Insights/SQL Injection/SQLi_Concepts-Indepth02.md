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
