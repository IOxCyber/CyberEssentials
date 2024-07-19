# Server-Side Vulnerability

## SQLi: `Manipulates a web application's database queries by injecting malicious SQL code.` [cheat-sheet1](https://portswigger.net/web-security/sql-injection/cheat-sheet) [Cheat-sheet2](https://www.invicti.com/blog/web-security/sql-injection-cheat-sheet/#SyntaxBasicAttacks)
- A web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database.
- Most SQL injection vulnerabilities `arise within the WHERE clause of a SELECT query.`
- Leads to DOS attack, steal info(pwd/cc info), affect the DB data, retrieve hidden data from DB.

## Affect of SQLi in Original Query:
- ![image](https://github.com/user-attachments/assets/bc261649-8844-4d6a-a78d-0d75334b5931)

## Impact:
- A successful SQL `injection attack can result in unauthorized access to sensitive data`, such as:
- Passwords.
- Credit card details.
- Personal user information.

> By levering SQL Injection, an attacker could bypass authentication, access, modify and delete data within a database.

---
---

# SQLi Types:
- SQL Injection can be classified into..
- 3 major categories – `In-band SQLi, Inferential SQLi (Blind SQLi) and Out-of-band SQLi.`

## 1. In-band SQLi (Classic SQLi):
- Definition: Attack where the same communication channel is used to both launch the attack and gather results.

### Types:
- 1. Error-based SQLi: Uses error messages to gain database information.
- 2. Union-based SQLi: Combines results of multiple SELECT statements into a single result.

- Impact: `Allows attackers to bypass authentication, access, modify, and delete data.`
- Prevention: `Disable detailed error messages on live sites, use parameterized queries`, and employ ORM (Object-Relational Mapping) frameworks.


## 2. Inferential SQLi (Blind SQLi):
- Definition: Attack where data is not directly transferred, but inferred through responses and behaviors.

### Types:
- 1. Boolean-based Blind SQLi: Uses true/false responses to infer database structure.
- 2. Time-based Blind SQLi: Uses response delays to infer database information.

- Impact: Just as dangerous as other SQLi types but takes longer to exploit.
- Prevention: Use parameterized queries, employ input validation and sanitization, and use security testing tools.


## 3. Out-of-band SQLi:
- Definition: Uses different communication channels to launch the attack and gather results.

### Types:
- 1. Microsoft SQL Server’s xp_dirtree: Makes DNS requests to an attacker-controlled server.
- 2. Oracle Database’s UTL_HTTP: Sends HTTP requests from SQL/PLSQL to an attacker-controlled server.

- Impact: Exploits features like DNS or HTTP requests, relies on database server capabilities.
- Prevention: Disable or restrict the use of database functions that can make external requests, implement strong access controls, and monitor for suspicious outbound traffic.

## EXTRAS: Database-specific syntax:
- On Oracle, `every SELECT query must use the FROM` keyword and specify a valid table. There is a built-in table on Oracle called dual which can be used for this purpose.
- eg. `' UNION SELECT NULL FROM DUAL--`
