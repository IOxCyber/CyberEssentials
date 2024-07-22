# 1. Identification and Authentication Failures `Failures in correctly identifying and authenticating users, leading to unauthorized access.`
- OWASP Category: A07:2021 - `Identification and Authentication Failures`

## Type:
```
Weak password policies
Lack of multi-factor authentication
Exposed credentials
Improper session handling
```

## Preventions:
```
Enforce strong password policies
Implement multi-factor authentication
Securely store and handle credentials
Use secure session management practices
```

## Detection/Testing Methods:
```
Automated tools for scanning weak passwords
Manual testing for multi-factor authentication enforcement
Reviewing password storage mechanisms
```

# 2. Broken Authentication: `allowing attackers to compromise passwords, keys, or session tokens`
- OWASP Category: A02:2021 - Broken Authentication


## Preventions:
```
Implement account lockout mechanisms
Use strong password policies and secure storage
Secure password recovery processes
```

## Detection/Testing Methods:
```
Automated tools to brute-force login attempts
Manual testing for password recovery weaknesses
Reviewing authentication flow for vulnerabilities
```

# 3. Broken Authentication and Session Management: `Flaws in managing user authentication and sessions`
- This leads to session hijacking or fixation attacks.

## Type:
```
Session fixation
Session hijacking
Insecure session storage
```

## Preventions:
```
Use secure session cookies with attributes like HttpOnly and Secure
Regenerate session IDs after login
Invalidate sessions after logout or inactivity
```

## Detection/Testing Methods:
```
Automated tools for session management testing
Manual testing for session hijacking and fixation
Reviewing session management code and configuration
```

# Extras:
> Session tokens are `unique identifiers assigned to a user session after a successful authentication.`
> Used in State Management, Security.

## Workflow Example of Sessions in a Site:
```
Initial Access:
User visits the news site.
No session is generated.


Login Attempt:
User logs in with credentials.
Server authenticates the user and generates a session token.
Server sends the session token to the client in a cookie.


Authenticated Session:
User navigates the site, reads articles, and accesses features available to logged-in users.
Each request from the client includes the session token, which the server validates.


Session Management:
The server monitors the session’s validity, manages session expiration, and may regenerate tokens if necessary.

Logout:
User logs out.
The server invalidates the session token and informs the client to remove the session token from storage.
```
