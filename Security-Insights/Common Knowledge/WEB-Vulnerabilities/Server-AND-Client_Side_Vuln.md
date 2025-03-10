# 1. Client-Side Vulnerabilities → Affect the user's browser or application.
- Occurs on the user's device (browser, mobile app, or local software) due to insecure code execution.

# 2. Server-Side Vulnerabilities → Affect the web server or backend systems.
- Occurs on the web server, database, or backend systems. Attackers exploit weak backend security to gain unauthorized access, modify data, or crash services.


## Client-Side Vulnerabilities:
```
Cross-Site Scripting (XSS)
Cross-Site Request Forgery (CSRF)
Unvalidated Redirects and Forwards
Information Leakage and Improper Error Handling (can affect both client and server, but often the exposure is on the client side)
Unvalidated Input (can affect both client and server, but often starts on the client side)
Buffer Overflow (typically client-side when affecting browser or local applications, but can be server-side in web server context)
```

## Server-Side Vulnerabilities:
```
SQL Injection (SQLi)
XML External Entities (XXE)
Broken Access Control
Insecure Direct Object References (IDOR)
Security Misconfiguration
Insecure Design
Identification and Authentication Failures
Vulnerable and Outdated Components
Security Logging and Monitoring Failures
Server-Side Request Forgery (SSRF)
Software and Data Integrity Failures

Injection
Injection Flaws
Malicious File Execution
Insecure Deserialization
Broken Authentication
Broken Authentication and Session Management
Failure to Restrict URL Access
Missing Function Level Access Control
Cryptographic Failures
Insecure Cryptographic Storage
Insufficient Transport Layer Protection
Sensitive Data Exposure
Insecure Configuration Management
Insecure Storage
Insecure Communications
Improper Error Handling (typically server-side)
Insufficient Logging and Monitoring
Application Denial of Service
```
