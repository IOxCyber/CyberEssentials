### The Open Web Application Security Project: [More](https://owasp.org/www-project-top-ten/)
- a standard awareness document for developers and web application security.
- a widely recognized and respected list of the top 10 most critical web application security risks.
- <img width="256" alt="image" src="https://user-images.githubusercontent.com/40174034/235904458-de7f5b19-326d-4113-9f85-82d2d3cb5dc1.png">
 
## 1. Broken Access Control:
- `Unauthorized information disclosure, modification, or destruction` of all data or performing a business function outside the user's limits.
- Prevention: Principle of `least privilege, deny by default`, parameter tampering, and avoiding modifying API requests.

## 2. Cryptographic Failures:
- `Weaknesses in the implementation or use of cryptographic algorithms` and protocols to protect sensitive data eg. data in transit and at rest, passwords, credit card numbers, health records, personal information, and business secrets.

> Avoid outdated `weak encryption algorithms, such as DES, MD5, SHA1, PKCS number 1 v1.5`

### Prevention:
- Encrypt all sensitive data at rest, `use of strong Algo. eg. AES, RSA, or SHA-256, TLS with forward secrecy (FS)`
- Store passwords using strong adaptive and salted `hashing functions with a work factor (delay factor), such as Argon2, scrypt, bcrypt or PBKDF2.`

## 3. Injection:
- SQL, NoSQL, OS command, Object Relational Mapping (ORM), LDAP, and Expression Language (EL) or Object Graph Navigation Library (OGNL) injection.

### Prevention:
- use a safe API, which avoids using the interpreter entirely, provides a parameterized interface, or migrates to Object Relational Mapping Tools (ORMs).
- Use positive server-side input validation.
- Use LIMIT and other SQL controls within queries to prevent mass disclosure of records in case of SQL injection.
  
## 4. Insecure Design:
- `missing or ineffective control design.`
- Secure Design: `code is robustly designed and tested to prevent known attack methods`
### Prevention: 
- Establish and use a secure development lifecycle.
- Use threat modeling for critical authentication, access control, business logic.
- Write unit and integration tests to validate that all critical flows

## 5. Security Misconfiguration:
- `Unnecessary features are enabled or installed` (e.g., unnecessary ports, services, pages, accounts, or privileges).
- `Error handling reveals` stack traces or other `overly informative error` messages to users.
- `software is out of date or vulnerable`

### Prevention:
- Remove or do not install unused features and frameworks
- patch management process, Review cloud storage permissions

## 6. Vulnerable and Outdated Components:
-  `software is vulnerable, unsupported, or out of date.`
-  If you do not scan for vulnerabilities regularly.

### Prevention:
- `Remove unused dependencies, unnecessary features, components, files, and documentation.`
- Only obtain components from official sources over secure links.

## 7. Identification and Authentication Failures:
- Uses `weak or ineffective credential recovery and forgot-password processes`
- Uses `plain text, unencrypted, or weakly hashed passwords data stores`
- Does not correctly invalidate Session IDs. User sessions or authentication tokens
 
### Prevention:
- Implement multi-factor authentication (prevent stuffing, brute force, and stolen credential reuse attacks)
- Align password length, complexity, and rotation policies.
- Ensure registration, credential recovery, and API pathways are hardened against account enumeration attacks[^1]

## 8. Software and Data Integrity Failures:
- `Software and data integrity failures relate to code and infrastructure` that do not protect against integrity violations.
- An `insecure CI/CD pipeline` can introduce the potential for unauthorized access, malicious code, or system compromise.

### Prevention:
- `Use digital signatures[^2] or similar mechanisms to verify the software or data.`
- Ensure libraries and dependencies are using trusted repositories.
- review process for code and configuration changes.

## 9. Security Logging and Monitoring Failures:
- `Auditable events are not logged` eg. such as logins, failed logins, and high-value transactions.
- `Warnings and errors generate no, inadequate, or unclear log messages.`
- The application cannot detect, escalate, or alert for active attacks in real-time or near real-time

### Prevention:
- establish effective monitoring and alerting such that suspicious activities are detected and responded to quickly.
- Ensure all login, access control, and server-side input validation failures can be logged.

## 10. Server-Side Request Forgery (SSRF):
- `Tricking a server into making a request on behalf of user`
- Occur when `a web application/server is fetching a remote resource without validating the user-supplied URL.`
- SSRF occurs when an attacker `manipulates the server to make requests to internal systems or restricted resources` that should not be accessible.

- eg. Imagine you're using an online shopping website. When you visit a product page, the website displays an image of the product. The website fetches the image from a different server to show it to you.
- If the site is vulnerable to SSRF then it'll be exposing sensitive information such as user data, financial records, or even administrative systems.

### Prevention:
- `Implement defense in depth` (Application to Network Layer)
- `Enforce “deny by default”` firewall policies or network access control rules.
- implementing proper security measures such as input validation, whitelisting or blacklisting of allowed URLs, and restricting access to internal resources.

[^1]: Allows an attacker to determine the validity/Existence of user accounts(username & password) on a system or application & leads to password guessing, credential stuffing, or targeted phishing attacks.
[^2]: cryptographic mechanisms used to provide authenticity, integrity, and non-repudiation to digital documents or messages. Digital signatures are a fundamental component of PKI.


