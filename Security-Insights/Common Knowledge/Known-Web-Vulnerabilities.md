## Zero-Day:
- Zero-day (0 day) vulnerability refers to a security vulnerability for which no mitigation or patch is available at the time it is disclosed or made public.

## 1. Cross-Site Request Forgery (CSRF): `forces an end user to execute unwanted actions on a web application in which they’re currently authenticated.`
> AKA XSRF, “Sea Surf”, Session Riding, Cross-Site Reference Forgery, and Hostile Linking, One-Click attack.
- An attack that forces authenticated users to submit a request to a Web application against which they are currently authenticated eg. using user’s session cookie, IP address, Windows domain credentials.
- CSRF attacks **exploit the trust a Web application has** in an authenticated user.

- Example:
- a user is logged into their banking website. While still authenticated, the user visits a malicious website. The malicious site, through embedded code, forces the user's browser to perform actions (e.g., transferring money) on the banking site without the user's knowledge.

## 2. Cross-site scripting (XSS)
- An attack in which an attacker injects malicious executable scripts into the code of a trusted application or website.


## 3. [Prototype pollution](https://portswigger.net/web-security/prototype-pollution/what-is-prototype-pollution):
- JavaScript vulnerability that enables an attacker to add arbitrary properties to global object prototypes, which may then be inherited by user-defined objects.
- Arise when a JavaScript function recursively merges an object containing user-controllable properties into an existing object, **without first sanitizing the keys**.
- Due to the special meaning of __proto__ in a JavaScript context, the merge operation may assign the nested properties to the object's prototype instead of the target object itself.
- The attacker can pollute the prototype with properties containing harmful values.
