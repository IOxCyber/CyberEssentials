# Vertical Privilege Escalation


## 1. [Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)
- The dev didn't implement the controls to restrict the Admin Panel, anyone can access it.
- Append robots.txt in `academy.net/robots.txt`
- It will show the rules for web crawlers
- [image](https://github.com/user-attachments/assets/ab5ce686-303c-41f5-b685-726033779551)


## 2. [Unprotected admin functionality with unpredictable URL](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality-with-unpredictable-url)
- This lab has an unprotected admin panel. It's located at an unpredictable location, but the location is disclosed somewhere in the application.
- The admin path is hidden in <script> tag of page source.
- ![image](https://github.com/user-attachments/assets/9d5e7ec8-3671-4073-8ccb-c9dc2a503f63)

## 3. [User role controlled by request parameter](https://portswigger.net/web-security/access-control/lab-user-role-controlled-by-request-parameter)
- Vuln request parameter: https://0a6c00af03d05e2a82a5b5bf00930027.web-security-academy.net/`my-account?id=wiener`
- Try accessing Admin Panel: `web-security-academy.net/admin` > Capture request in BurpSuite
- forgeable cookie:![image](https://github.com/user-attachments/assets/672f89f5-17e1-4dcf-8bf0-6cf9aa76dde9)
- Modified Cookies: ![image](https://github.com/user-attachments/assets/a874b6db-013a-470e-98e6-1ef8218ae870)
- Now, Modify the Queries in the Browser > Storage > Cookie
- ![image](https://github.com/user-attachments/assets/ad9cbc27-5391-4474-a94c-ad095455d200)


## 4. [User role can be modified in user profile](https://portswigger.net/web-security/access-control/lab-user-role-can-be-modified-in-user-profile)
- This lab has an admin panel at /admin. It's only accessible to logged-in users with a roleid of 2.
- Login to site using given creds in Lab > Capture the Email update request > observe the JSON data {} > Update your account "roleid"=2 > Send it & In browser copy the request > try accessing /admin by appending in URL > del user > done
- ![image](https://github.com/user-attachments/assets/2c42d867-9c2e-4567-a866-891bb8dcc716)


## 5. [LAter](https://portswigger.net/web-security/access-control/lab-url-based-access-control-can-be-circumvented)







## Robots.txt: `a way to control indexing and crawling by search engines`
- The robots.txt file is `not a security mechanism.`
- `publicly accessible`, can be viewed by navigating to http://example.com/robots.txt.
- Prevent search engines from indexing certain parts of their website.
- Manage server load by restricting access to resource-intensive pages.
- Keep certain site sections private or hidden from search engine results.

```
Example:

User-agent: *
Disallow: /private/
Disallow: /tmp/
Disallow: /test/

User-agent: Googlebot
Allow: /public/
Disallow: /not-for-google/
```
