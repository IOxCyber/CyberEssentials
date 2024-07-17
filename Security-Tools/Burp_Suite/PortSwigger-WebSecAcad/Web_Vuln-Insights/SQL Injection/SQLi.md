# Server-Side Vulnerability

## SQLi: `Manipulates a web application's database queries by injecting malicious SQL code.` [cheat-sheet1](https://portswigger.net/web-security/sql-injection/cheat-sheet) [Cheat-sheet2](https://www.invicti.com/blog/web-security/sql-injection-cheat-sheet/#SyntaxBasicAttacks)
- A web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.
- Most SQL injection vulnerabilities `arise within the WHERE clause of a SELECT query.`
- Leads to DOS attack, steal info(pwd/cc info), affect the DB data, retrieve hidden data from DB.

## Affect of SQLi in Original Query:
- ![image](https://github.com/user-attachments/assets/bc261649-8844-4d6a-a78d-0d75334b5931)
