## Preventing DOM-Based XSS
- Sanitize user inputs before inserting them into the DOM. Here’s how you can modify the code to prevent the vulnerability:
```
Using textContent Instead of innerHTML:

document.getElementById('submitButton').addEventListener('click', function() {
    const userInput = document.getElementById('userInput').value;
    document.getElementById('welcomeMessage').textContent = 'Welcome, ' + userInput + '!';
});
```

> By using textContent instead of innerHTML, the input is treated as plain text, preventing any HTML or JavaScript from being executed.

