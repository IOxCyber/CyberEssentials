## 1. SQL Injection (SQLi)
- Test Case 1: Testing for Basic SQL Injection

```
Objective: Identify if input fields are vulnerable to SQL injection.
Steps:
Intercept the Request: Use Burp Suite Proxy to capture a request containing user input.
Send to Repeater: Right-click on the request and send it to Repeater.
Modify Input: Inject SQL payloads like ' OR 1=1 -- or ; DROP TABLE users; -- into input fields.
Observe Response: Send the modified request and analyze the response for SQL errors or unexpected behavior.
```

- Test Case 2: Testing for Blind SQL Injection
```
Objective: Identify blind SQL injection vulnerabilities.
Steps:
Capture Request: Intercept a request with user input.
Send to Intruder: Right-click and send the request to Intruder.
Set Payload Positions: Mark the input fields where you suspect SQL injection.
Add Payloads: Use a list of time-based SQL payloads like 1 AND SLEEP(5).
Start Attack: Analyze response times to identify delayed responses, indicating potential blind SQL injection.
```

## 2. Cross-Site Scripting (XSS)

- Test Case 1: Testing for Reflected XSS
```
Objective: Identify reflected XSS vulnerabilities.
Steps:
Intercept the Request: Use Burp Suite Proxy to capture a request containing user input.
Send to Repeater: Right-click and send it to Repeater.
Modify Input: Inject XSS payloads like <script>alert('XSS')</script> into input fields.
Observe Response: Send the modified request and observe if the payload is reflected in the response and executed.
```

- Test Case 2: Testing for Stored XSS
```
Objective: Identify stored XSS vulnerabilities.
Steps:
Intercept Request: Capture a request that saves user input (e.g., a comment form).
Send to Repeater: Right-click and send it to Repeater.
Modify Input: Inject XSS payloads like <script>alert('Stored XSS')</script>.
Save Input: Send the modified request to store the payload.
Verify Storage: Navigate to the part of the application where the input is displayed and check if the payload is executed.
```

## 3. Cross-Site Request Forgery (CSRF)
- Test Case 1: Testing for CSRF in Form Submissions

```
Objective: Identify CSRF vulnerabilities in form submissions.
Steps:
Capture Request: Intercept a form submission request using Burp Suite Proxy.
Send to Repeater: Send the request to Repeater.
Craft CSRF Payload: Manually create an HTML form that submits the same request parameters.
Test Execution: Open the crafted form in a browser without being authenticated to the site and observe if the action is performed.
```

## 4. Command Injection
- Test Case 1: Testing for Command Injection
```
Objective: Identify command injection vulnerabilities.
Steps:
Capture Request: Intercept a request with parameters that might interact with the OS.
Send to Repeater: Send the request to Repeater.
Modify Input: Inject command payloads like ; ls or && whoami into the parameters.
Observe Response: Analyze the response for signs of command execution output.
```

## 5. File Inclusion (LFI/RFI)

- Test Case 1: Testing for Local File Inclusion (LFI)

```
Objective: Identify LFI vulnerabilities.
Steps:
Capture Request: Intercept a request that includes a file path parameter.
Send to Repeater: Send the request to Repeater.
Modify Path: Inject LFI payloads like ../../etc/passwd into the file path parameter.
Observe Response: Check if sensitive files are included and displayed in the response.
```

Test Case 2: Testing for Remote File Inclusion (RFI)
```
Objective: Identify RFI vulnerabilities.
Steps:
Capture Request: Intercept a request that includes a file path parameter.
Send to Repeater: Send the request to Repeater.
Modify Path: Inject RFI payloads with URLs pointing to external scripts.
Observe Response: Check if external scripts are included and executed.
```
