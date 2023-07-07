## SQLi: a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.
- can leads to DOS attack, steal info(pwd/cc info)

## How to detect: Test in User input & look for error/outputs
- <img width="500" alt="image" src="https://github.com/cybersome/CyberEssentials/assets/40174034/46b66669-863d-4796-937a-a11da9bbbd84">
> single-quote(') character is used to properly format the injected payload as a string literal within the original query.

## Injection Examples:
### `Retrieving hidden data`, where you can modify a SQL query to return additional results.
1. Testing for boolean-based attacks:
- `'OR 1=1 --` - This payload appends an OR condition that always evaluates to true, commenting out the remaining portion of the original query.
- `'OR 'x'='x` - This payload compares a string with itself, resulting in a true condition.

2. Testing for time-based attacks:
- `'OR SLEEP(5) --` - This payload tries to induce a delay of 5 seconds in the SQL query execution by using the SLEEP function. If the website is vulnerable, it will take longer to respond.
- `'OR BENCHMARK(10000000,SHA1(1)) --` - This payload attempts to measure the time taken to execute the SHA1 function a large number of times, causing a significant delay if the SQL injection is successful.

3. Testing for error-based attacks:
- `'OR 1=1; DROP TABLE users; --` - This payload combines a valid condition (1=1) with a malicious action (DROP TABLE users), potentially causing an error and deleting the "users" table.
-  `'OR 1=1 UNION ALL SELECT NULL, CONCAT(username,':',password) FROM users --` - This payload attempts to perform a UNION-based SQL injection to retrieve the usernames and passwords from the "users" table.


### `Subverting/interfere with application logic`, change a query to interfere with the application's logic.


- `UNION attacks, retrieve data from different database tables.`
- `Blind SQL injection`, where the results of a query you control are not returned in the application's responses.






















## Solution:
- Lab 1: Retrieval of Hidden Data(Where) `Modify the category parameter, giving it the value '+OR+1=1--`
- Lab 2: `Modify the username parameter, giving it the value: administrator'--` or `enter ' OR 1=1-- in username & pwd field`
- Lab 3: 

