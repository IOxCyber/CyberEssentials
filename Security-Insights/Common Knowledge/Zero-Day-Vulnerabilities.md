## Zero-Day:
- Zero-day (0 day) vulnerability refers to a security vulnerability for which no mitigation or patch is available at the time it is disclosed or made public.
- A zero-day vulnerability refers to a security flaw in software or hardware that is unknown to the vendor or developer and, therefore, has not been patched or mitigated.
- `The term "zero-day" indicates that the developer has "zero days" to fix the issue because the vulnerability` is already known and potentially being exploited by attackers.

## 1. Cross-Site Request Forgery (CSRF): ` tricks users into performing unintended actions on authenticated websites.`
> AKA XSRF, Sea-Surf, Session Riding, One-Click Attack, Cross-Site Reference Forgery, Hostile Linking, Forced Browsing, and Session Theft, One-Click hack.
- The attacker `forged a request (Pwd change, Bank transfer etc) & embedded the link (eg. email)`, if Victim clicked the link then the hacker executes the forged request using Victim's session and performs actions on Server.
- Typically conducted using malicious social engineering, such as an email or link that tricks the victim into sending a forged request to a server using the victim session ID.
- Before executing an assault, a perpetrator typically studies an application in order to make a forged request appear as legitimate as possible.
- If the bank’s website is only using POST requests, it’s impossible to frame malicious requests using a <a> href tag. However, the attack could be delivered in a <form> tag with automatic execution of the embedded JavaScript.

## 2. Cross-Site Scripting (XSS) [more](https://www.cloudflare.com/en-gb/learning/security/threats/cross-site-scripting/) `injecting malicious code into a website to steal information or perform actions on behalf of a user`
- An attacker `injects malicious code, typically in the form of scripts(any client-side lang eg. JS) into a web application/a legitimate website`
- When other users access the application, the injected code is executed within their browsers, allowing the attacker to steal information, manipulate content, or perform other malicious activities.
- Two Types:
  - Reflected cross-site scripting: Malicious code is added onto the end of the URL of a website.
  - Persistent cross-site scripting: Malicious Code in comments forum or social media site.
- `cross-site scripting is a client-side code injection attack.`

## 3. [Prototype pollution](https://portswigger.net/web-security/prototype-pollution/what-is-prototype-pollution):
- JavaScript vulnerability that enables an attacker to add arbitrary properties to global object prototypes, which may then be inherited by user-defined objects.
- Arise when a JavaScript function recursively merges an object containing user-controllable properties into an existing object, **without first sanitizing the keys**.
- Due to the special meaning of __proto__ in a JavaScript context, the merge operation may assign the nested properties to the object's prototype instead of the target object itself.
- The attacker can pollute the prototype with properties containing harmful values.
