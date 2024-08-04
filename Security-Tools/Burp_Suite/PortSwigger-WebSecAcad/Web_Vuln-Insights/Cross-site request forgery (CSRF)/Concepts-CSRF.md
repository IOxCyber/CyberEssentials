# Cross Side Request Forgery:
- Web security vulnerability that allows an attacker to induce users to perform actions that they do not intend to perform.
- Impact: `attacker might be able to gain full control over the user's account.`

> Cross-site scripting (or XSS) allows an attacker to `execute arbitrary JavaScript within the browser of a victim user.`
###  `XSS > CSRF (Impact)`
> Cross-site request forgery (or CSRF) allows an attacker to `induce a victim user to perform actions that they do not intend to.`


# How does CSRF work `Conditions for Exploitation`
1. **Relevant Action**:
   - The attacker induces an application action, such as modifying permissions or changing a user's password.

2. **Cookie-Based Session Handling**:
   - The application relies solely on session cookies for user identification, with no additional session tracking or request validation mechanisms.

3. **No Unpredictable Request Parameters**:
   - Requests to perform the action lack parameters that the attacker cannot guess. For example, changing a password without needing the current password.

```
eg.
This meets the conditions required for CSRF:

The action of changing the email address on a user's account is of interest to an attacker. 
The application uses a session cookie to identify which user issued the request. There are no other tokens or mechanisms in place to track user sessions.
The attacker can easily determine the values of the request parameters that are needed to act.

POST /email/change HTTP/1.1
Host: vulnerable-website.com
Content-Type: application/x-www-form-urlencoded
Content-Length: 30
Cookie: session=yvthwsztyeQkAPzeQ5gHgTvlyxHfsAfE

email=wiener@normal-user.com
```



### With these conditions in place, the attacker can construct a web page containing the following HTML:
```
<html>
    <body>
        <form action="https://vulnerable-website.com/email/change" method="POST">
            <input type="hidden" name="email" value="pwned@evil-user.net" />
        </form>
        <script>
            document.forms[0].submit();
        </script>
    </body>
</html>
```
### If a victim user visits the attacker's web page, the following will happen:
```
The attacker's page will trigger an HTTP request to the vulnerable website.
If the user is logged in to the vulnerable website, their browser will automatically include their session cookie in the request (assuming SameSite cookies are not being used).
The vulnerable website will process the request in the normal way, treat it as having been made by the victim user, and change their email address.
```

> The easiest way to construct a CSRF exploit is using the CSRF PoC generator that is built in to Burp Suite Professional.


# How to deliver a CSRF exploit:
- Typically, the attacker will place the malicious HTML onto a website that they control, and then induce victims to visit that website.
- This might be done by `feeding the user a link to the website, via an email or social media message.`







