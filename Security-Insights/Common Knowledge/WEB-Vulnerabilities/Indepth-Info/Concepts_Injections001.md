# 1. SQL Injection: `Injecting the SQL cmds in App's Entry point to extract data from Server`
- `OWASP Category: A03:2021 - Injection`

## Subtype:
```
SQL Injection
Command Injection
LDAP Injection
NoSQL Injection
Injection Flaws
```

### Example:
```
-- Vulnerable code
query = "SELECT * FROM users WHERE username = '" + userInput + "'";

-- Malicious input
userInput = "' OR '1'='1";

-- Resulting query
"SELECT * FROM users WHERE username = '' OR '1'='1'";
```

# Preventions:
```
Use parameterized queries or prepared statements.
Validate and sanitize inputs.
Use ORM frameworks to abstract database interactions.
Apply least privilege principle to database accounts.
```

# 2. Server-Side Request Forgery (SSRF) `Tricks a server to make calls to internal servers & expose internal/private data`
- `OWASP Category: A10:2021 - Server-Side Request Forgery (SSRF)`

### Example:
```
import requests

# Vulnerable code
url = input("Enter a URL to fetch data from: ")
response = requests.get(url)

# Malicious input
url = "http://localhost/admin"
```

# Preventions:
```
Validate and sanitize all URLs.
Implement network segmentation and access controls.
Use allow-lists for permitted domains.
Disable unused URL schemas and methods.
```

# XML External Entities (XXE) ``
- Occurs when XML parsers process external entities within XML documents, leading to potential data exposure and execution of remote requests.
- OWASP Category: A04:2021 - Insecure Design
- `XML: markup language to store and transport data rather than display it. `

# Preventions:
```
Disable DTDs:
Disable DTD processing in the XML parser to prevent external entity resolution.

Use Secure Libraries:
Use libraries and frameworks that are not vulnerable to XXE by default.

Input Validation:
Validate and sanitize XML inputs to ensure they do not contain DTDs or external entities.

Use Less Complex Formats:
Consider using simpler data formats like JSON if XML's advanced features are not needed.
```

## Testing Methods for XXE:
```
Static Code Analysis:
Use tools to analyze code for vulnerabilities related to XML parsing.

Dynamic Application Security Testing (DAST):
Perform security testing on the running application to identify XXE vulnerabilities.

Manual Code Review:
Manually review code to identify places where XML is parsed and ensure DTD processing is disabled.

Fuzz Testing:
Send specially crafted XML inputs to the application to see if it processes external entities.
```

### Example:
```
<?xml version="1.0" ?>
<!DOCTYPE foo [ <!ELEMENT foo ANY >
<!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<foo>&xxe;</foo>
```

### DTD: Document Type Definition. 
- It is a `set of rules that defines the structure and the legal elements and attributes of an XML document.`
- DTDs can define external entities, which reference external files or URLs. 

