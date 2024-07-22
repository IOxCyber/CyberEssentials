# Client-Side Vulnerability [Cheatsheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)

## Cross-site scripting (XSS):
-  Allow an attacker to masquerade as a victim user, to carry out any actions that the user can perform, and to access any of the user's data.

## Impact:
- An attacker who exploits a cross-site scripting vulnerability is typically able to:
```
Impersonate or masquerade as the victim user.
Carry out any action that the user is able to perform.
Read any data that the user is able to access.
Capture the user's login credentials.
Perform virtual defacement of the web site.
Inject trojan functionality into the web site.
```

## 3 main types of XSS attacks

### 1. Reflected XSS
- where the malicious script `comes from the current HTTP request.`
- It arises `when an application receives data in an HTTP request and includes that data within the immediate response` in an unsafe way.
- simplest variety of cross-site scripting.
- eg. `https://insecure-website.com/status?message=All+is+well.<p>Status: All is well.</p>`

### 2. Stored XSS
- where the malicious script `comes from the website's database.`
- AKA persistent or second-order XSS.
- It arises `when an application receives data from an untrusted source and includes that data within its later HTTP responses` in an unsafe way.
- for example, comments on a blog post, user nicknames in a chat room, or contact details on a customer order, a webmail application displaying messages received over SMTP, a marketing application displaying social media posts, or a network monitoring application displaying packet data from network traffic.
- eg. `<p>Hello, this is my message!</p>`

### 3. DOM-based XSS
-  `where the vulnerability exists in client-side code rather than server-side code.`
- DOM-based vulnerabilities arise `when a website contains JavaScript that takes an attacker-controllable value, known as a source, and passes it into a dangerous function, known as a sink.`
- Craft a DOM-based JS code > Distribute to User > Execute Code

> the most effective way to avoid DOM-based vulnerabilities is to avoid allowing data from any untrusted source to dynamically alter the value that is transmitted to any sink.

---
---

// Use textContent instead of innerHTML to avoid interpreting HTML
document.getElementById('greeting').textContent = 'Welcome, ' + user + '!';
```
- `textContent` ensures that any user `input is treated as plain text and not HTML` code.


