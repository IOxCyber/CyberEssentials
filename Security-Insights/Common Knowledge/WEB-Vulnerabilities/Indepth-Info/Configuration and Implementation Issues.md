# 1. Security misconfiguration
- Occurs when security settings are not implemented correctly, leaving applications vulnerable to attacks.
- OWASP Category: `A05:2021 - Security Misconfiguration`

```
Default Configurations: Using default settings and credentials.
Unnecessary Features Enabled: Features like directory listings, debug mode, or unnecessary services enabled.
Incomplete or Ad-Hoc Configurations: Inconsistent or incomplete configurations across the application and its environment.
```

## Preventions:
```
Disable unnecessary features and services.
Use security configuration guides and checklists.
Regularly update and patch systems.
```

## Detection/Testing Methods:
```
Automated security scanners like Nessus/Qualys or OpenVAS.
Manual configuration reviews and audits.
Penetration testing.
```

 # 2. Directory Traversal
- Directory traversal `allows attackers to access restricted directories and execute commands outside of the web server's root directory.`
- OWASP Category: `A01:2021 - Broken Access Control`

### Subtypes of this vulnerability:
- Path Traversal: Using relative path sequences like ../ to navigate directories.
- Absolute Path Traversal: Using absolute paths to access directories directly.

## Preventions:
```
Sanitize and validate all user inputs.
Use a whitelist of allowed files and directories.
Employ secure coding practices and frameworks.
```

## Detection/Testing Methods:
```
Automated tools like OWASP ZAP or Burp Suite.
Manual testing for path traversal sequences.
Code reviews focusing on file handling functions.
```

# 3. Insecure Design
- Insecure design refers to the `absence of security controls and principles during the design phase` of the software development lifecycle.
- OWASP Category: `A04:2021 - Insecure Design`

### Example:
```
# No encryption for sensitive data storage
password = "user_password"
database.store(password)

# Encryption for sensitive data storage
import hashlib

password = "user_password"
hashed_password = hashlib.sha256(password.encode()).hexdigest()
database.store(hashed_password)
```

## Preventions:
```
Integrate security into the design phase (e.g., threat modeling).
Follow security best practices and design patterns.
Regularly review and update design documentation.
```

## Detection/Testing Methods:
```
Design reviews and threat modeling sessions.
Security architecture assessments.
Use of automated design analysis tools.
```

# 4. Vulnerable and Outdated Components:
- Using `components with known vulnerabilities` that may compromise the security of the entire system.
- OWASP Category: `A06:2021 - Vulnerable and Outdated Components`

```
Outdated Libraries/Frameworks: Using old versions with known security issues.
Unpatched Software: Failure to apply security patches to software components.
```

## Preventions:
```
Regularly update and patch software components.
Use automated tools to identify vulnerabilities in dependencies.
Maintain an inventory of all software components.
```

## Detection/Testing Methods:
```
Dependency scanning tools like OWASP Dependency-Check or Snyk.
Manual review of component versions and known vulnerabilities.
Regular penetration testing and security assessments.
```

# 5. Insecure Configuration Management
- `failure to configure applications, servers, and networks securely.`
- Default Credentials: Using default usernames and passwords.
- Unrestricted Access: Overly permissive access controls.

## Preventions:
```
Change default credentials immediately after installation.
Apply the principle of least privilege.
Regularly audit and review configuration settings.
```

## Detection/Testing Methods:
```
Automated configuration scanners like Lynis.
Manual audits and configuration reviews.
Regular security assessments and penetration testing.
```

# 6. Insecure Storage
- Plaintext Storage: Storing sensitive data in plaintext.
- Weak Encryption: Using insufficient or outdated encryption methods.
- `A03:2021 - Sensitive Data Exposure`

## Preventions:
```
Use strong encryption methods for sensitive data.
Implement secure key management practices.
Regularly review and update encryption algorithms.
```

## Detection/Testing Methods:
```
Security code reviews focused on data storage.
Automated tools like Veracode or Checkmarx.
Penetration testing targeting data storage mechanisms.
```

# 7. Insecure Communications
- Occur when `data is transmitted without proper encryption`, allowing attackers to intercept and manipulate it.
- OWASP Category: `A02:2021 - Cryptographic Failures`
- Unencrypted Transmission: Data transmitted in plaintext.
- Weak Encryption Protocols: Using outdated or insecure protocols like SSL 2.0/3.0.

## Preventions:
```
Use strong encryption protocols like TLS 1.2/1.3.
Implement HTTPS for all communications.
Regularly update and patch cryptographic libraries.
```

## Detection/Testing Methods:
```
Automated tools like SSL Labs for SSL/TLS analysis.
Manual inspection of communication channels.
Penetration testing focusing on data transmission.
```

### Common prevention and detection techniques:

| **Prevention Techniques**                   | **Detection Techniques**                       |
|---------------------------------------------|------------------------------------------------|
| Regularly Update and Patch Systems          | Automated Vulnerability Scanning               |
| Use Secure Defaults                         | Log Monitoring and Analysis                    |
| Implement Least Privilege                   | Regular Security Assessments                   |
| Harden Configurations                       | Configuration Audits                           |
| Enable Security Features                    | Intrusion Detection and Prevention Systems     |
| Use Strong Authentication and Authorization | Security Baseline Validation                   |
| Perform Regular Security Audits and Assessments | Patch Management Tools                     |
| Automate Security Configuration             | Code Reviews and Static Analysis               |
| Segmentation and Isolation                  | Threat Intelligence                            |
| Document and Enforce Security Policies      | Red Team Exercises                             |
