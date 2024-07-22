# Common Web-Vulnerabilities:

## 1. Server-Side Request Forgery (SSRF): `tricks servers into making unauthorized requests to internal resources`
- How Attacker finds: This could be a feature like fetching an image, making API calls, or accessing remote resources.
- The attacker identifies an input field or parameter where they can specify the URL or resource to be accessed by the server.
- The Attacker may use techniques like URL encoding or providing a specially crafted URL to mislead the server.

## 2. Cross-Site Request Forgery (CSRF): ` tricks users into performing unintended actions on authenticated websites.`
> AKA XSRF, Sea-Surf, Session Riding, One-Click Attack, Cross-Site Reference Forgery, Hostile Linking, Forced Browsing, and Session Theft, One-Click hack.
- The attacker `forged a request (Pwd change, Bank transfer etc) & embedded the link (eg. email)`, if Victim clicked the link then the hacker executes the forged request using Victim's session and performs actions on Server.
- Typically conducted using malicious social engineering, such as an email or link that tricks the victim into sending a forged request to a server using the victim session ID.
- Before executing an assault, a perpetrator typically studies an application in order to make a forged request appear as legitimate as possible.
- If the bank’s website is only using POST requests, it’s impossible to frame malicious requests using a <a> href tag. However, the attack could be delivered in a <form> tag with automatic execution of the embedded JavaScript.

```
Best practices/Prevention:
Logging off web applications when not in use
Securing usernames and passwords
Not allowing browsers to remember passwords
Avoiding simultaneously browsing while logged into an application
```
- <img width="500" alt="image" src="https://github.com/IOxCyber/EssentialsCy/assets/40174034/3af831d7-deb4-4542-9f50-2c503df06b61">

## 3. Cross-Site Scripting (XSS) [more](https://www.cloudflare.com/en-gb/learning/security/threats/cross-site-scripting/) `injecting malicious code into a website to steal information or perform actions on behalf of a user`
- An attacker `injects malicious code, typically in the form of scripts(any client-side lang eg. JS) into a web application/a legitimate website`
- When other users access the application, the injected code is executed within their browsers, allowing the attacker to steal information, manipulate content, or perform other malicious activities.
- Two Types:
  - Reflected cross-site scripting: Malicious code is added onto the end of the URL of a website.
  - Persistent cross-site scripting: Malicious Code in comments forum or social media site.
- `cross-site scripting is a client-side code injection attack.`

```
Impact: 
Hijack an account.
Spread web worms.
Capturing the keystrokes of a user
Redirecting a user to a malicious website
Access browser history and clipboard contents.
Control the browser remotely.
```
```
Prevention:
Always perform input validation and sanitization on input
Implement output encoding
Generate Token + Cookies
Follow the defense-in-depth principle
```

4. XML External Entity (XXE) Injection:
- XML (eXtensible Markup Language) is a markup language used to store and transport data.

5. Blind SQL Injection:
- Type of SQL injection attack that occurs when an application is vulnerable to SQL injection but the `results of the SQL queries are not directly returned to the attacker. Instead, the attacker relies on the application's behavior or response times` to infer information about the database.

6. 
