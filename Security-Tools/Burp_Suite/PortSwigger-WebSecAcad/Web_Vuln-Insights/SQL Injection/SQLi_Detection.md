# How to detect: 
### `You can detect SQL injection manually using a systematic set of tests against every entry point in the application.`
- Entry Ponits like `search field, login form, or any other input & Observe the errors/outputs.`

```
The single quote character ' and look for errors or other anomalies.
Boolean conditions such as OR 1=1 and OR 1=2, and look for differences in the application's responses.
Payloads designed to trigger time delays when executed within a SQL query, and look for differences in the time taken to respond.
OAST payloads designed to trigger an out-of-band network interaction when executed within a SQL query, and monitor any resulting interactions.
```
> single-quote(') character is used to properly format the injected payload as a string literal within the original query.

### Most SQL injection vulnerabilities `occur within the WHERE clause of a SELECT query`. 
- Most experienced testers are familiar with this type of SQL injection.
- Also, SQL injection vulnerabilities can occur at any location within the query, and within different query types. Some other common locations where SQL injection arises are:
```
In UPDATE statements, within the updated values or the WHERE clause.
In INSERT statements, within the inserted values.
In SELECT statements, within the table or column name.
In SELECT statements, within the ORDER BY clause.
```



