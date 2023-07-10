### The Open Web Application Security Project: [More](https://owasp.org/www-project-top-ten/)
- a standard awareness document for developers and web application security.
- a widely recognized and respected list of the top 10 most critical web application security risks.
- <img width="256" alt="image" src="https://user-images.githubusercontent.com/40174034/235904458-de7f5b19-326d-4113-9f85-82d2d3cb5dc1.png">
 
1. Broken Access Control:
- `Unauthorized information disclosure, modification, or destruction` of all data or performing a business function outside the user's limits.
- Prevention: Principle of `least privilege, deny by default`, parameter tampering, and avoid modifying API requests.

2. Cryptographic Failures:
- `Weaknesses in the implementation or use of cryptographic algorithms` and protocols to protect sensitive data eg. data in transit and at rest, passwords, credit card numbers, health records, personal information, and business secrets.

> Avoid outdated `weak encryption algorithms, such as DES, MD5, SHA1, PKCS number 1 v1.5`

### Prevention:
- Encrypt all sensitive data at rest, `use of strong Algo. eg. AES, RSA, or SHA-256, TLS with forward secrecy (FS)`
- Store passwords using strong adaptive and salted `hashing functions with a work factor (delay factor), such as Argon2, scrypt, bcrypt or PBKDF2.`

3. Injection:
- SQL, NoSQL, OS command, Object Relational Mapping (ORM), LDAP, and Expression Language (EL) or Object Graph Navigation Library (OGNL) injection.

### Prevention:
- use a safe API, which avoids using the interpreter entirely, provides a parameterized interface, or migrates to Object Relational Mapping Tools (ORMs).
- Use positive server-side input validation.
- Use LIMIT and other SQL controls within queries to prevent mass disclosure of records in case of SQL injection.
  
4. Insecure Design:
- `missing or ineffective control design.`
- Secure Design: `code is robustly designed and tested to prevent known attack methods`
### Prevention: 
- Establish and use a secure development lifecycle.
- Use threat modeling for critical authentication, access control, business logic.
- Write unit and integration tests to validate that all critical flows

5. Security Misconfiguration:
- `Unnecessary features are enabled or installed` (e.g., unnecessary ports, services, pages, accounts, or privileges).
- `Error handling reveals` stack traces or other `overly informative error` messages to users.
- `software is out of date or vulnerable`

### Prevention:
- Remove or do not install unused features and frameworks
- patch management process, Review cloud storage permissions

6. 
### Prevention:


7.
### Prevention:


8.
### Prevention:


9.
### Prevention:


10.
### Prevention:

