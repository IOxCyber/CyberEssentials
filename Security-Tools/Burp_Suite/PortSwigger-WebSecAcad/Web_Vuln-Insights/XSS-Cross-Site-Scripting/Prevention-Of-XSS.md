## Preventing DOM-Based XSS `Using textContent Instead of innerHTML`
- Sanitize user inputs before inserting them into the DOM. Here’s how you can modify the code to prevent the vulnerability:
```
document.getElementById('submitButton').addEventListener('click', function() {
    const userInput = document.getElementById('userInput').value;
    document.getElementById('welcomeMessage').textContent = 'Welcome, ' + userInput + '!';
});
```

- `Using textContent` instead of innerHTML, the `input is treated as plain text`, preventing any HTML or JavaScript from being executed.

# Effectively preventing XSS vulnerabilities is likely to involve a combination of the following measures:

## 1. Filter/Validate input on arrival: `inputs are treated as data rather than executable code.`
- At the point where user input is received, filter as strictly as possible based on what is expected or valid input.
- Validate all user inputs on both the client and server sides.
- Client Side: HTML `<input type="text" id="username" name="username" required pattern="[A-Za-z0-9]{5,15}">`
- Server Side: PHP `if (!preg_match("/^[A-Za-z0-9]{5,15}$/", $username))`

## 2: `Encode data on output`. 
- At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content.
- Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.
- `escape HTML special characters`

## 3 `Use appropriate response headers`. 
- To prevent XSS in HTTP responses that aren't intended to contain HTML or JavaScript. You can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way it was intend.
  - Content-Type: To treat the response as JSON only and not to try to interpret it as HTML or JavaScript by browser.
  - X-Content-Type-Options: The browser will not override the specified content type, thus preventing MIME-sniffing and reducing the risk of XSS attacks.

## 4. `Content Security Policy`
  - Security feature that helps by specifying which dynamic resources are allowed to load and execute.
  - CSP is implemented via an HTTP header sent by the server to the browser.
  - The `HTTP header contains directives` that define allowed `content sources` for various types of resources, such as scripts, styles, images, and more.
  - Example: `Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted.cdn.com; style-src 'self' https://trusted.cdn.com; img-src 'self' data:`
  - Self: means same-origin (same protocol, domain, and port)
```
Same Origin:
https://example.com/page1
https://example.com/page2
Both URLs share the same protocol (HTTPS), domain (example.com), and port (443, implied by HTTPS).


Different Origin:

https://example.com/page

http://example.com/page

The protocols are different (HTTPS vs. HTTP).

https://example.com/page

https://sub.example.com/page

The domains are different (example.com vs. sub.example.com).


https://example.com:443/page

https://example.com:8443/page

The ports are different (443 vs. 8443).
```


