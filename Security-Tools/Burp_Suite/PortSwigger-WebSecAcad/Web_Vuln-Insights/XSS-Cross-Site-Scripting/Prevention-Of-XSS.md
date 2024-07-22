## Preventing DOM-Based XSS `Using textContent Instead of innerHTML`
- Sanitize user inputs before inserting them into the DOM. Here’s how you can modify the code to prevent the vulnerability:
```
document.getElementById('submitButton').addEventListener('click', function() {
    const userInput = document.getElementById('userInput').value;
    document.getElementById('welcomeMessage').textContent = 'Welcome, ' + userInput + '!';
});
```

- `Using textContent` instead of innerHTML, the `input is treated as plain text`, preventing any HTML or JavaScript from being executed.

## Effectively preventing XSS vulnerabilities is likely to involve a combination of the following measures:

- `Filter input on arrival`. At the point where user input is received, filter as strictly as possible based on what is expected or valid input.

- `Encode data on output`. At the point where user-controllable data is output in HTTP responses, encode the output to prevent it from being interpreted as active content. Depending on the output context, this might require applying combinations of HTML, URL, JavaScript, and CSS encoding.

- `Use appropriate response headers`. To prevent XSS in HTTP responses that aren't intended to contain any HTML or JavaScript, you can use the Content-Type and X-Content-Type-Options headers to ensure that browsers interpret the responses in the way you intend.

- `Content Security Policy`. As a last line of defense, you can use Content Security Policy (CSP) to reduce the severity of any XSS vulnerabilities that still occur.

