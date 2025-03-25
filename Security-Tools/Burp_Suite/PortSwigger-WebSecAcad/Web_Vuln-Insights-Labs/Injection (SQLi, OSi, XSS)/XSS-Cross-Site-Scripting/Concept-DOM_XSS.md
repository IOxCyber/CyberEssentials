# DOM-based XSS:
-  `where the vulnerability exists in client-side code rather than server-side code.`
- DOM-based vulnerabilities arise `when a website contains JavaScript that takes an attacker-controllable value, known as a source, and passes it into a dangerous function, known as a sink` that supports dynamic code execution, such as eval() or innerHTML. 
- Craft a DOM-based JS code > Distribute to User > Execute Code
- `A Source (value) & A Sink (function).`

> the most effective way to avoid DOM-based vulnerabilities is to avoid allowing data from any untrusted source to dynamically alter the value that is transmitted to any sink.

### Source & Sink:

## 1. Sources `Value/Data`
- A source is a JavaScript property that accepts data that is potentially attacker-controlled.
- This could be `user input, URL parameters, or any other data coming from an external or untrusted source.`
- Ultimately, `any property that an attacker can control is a potential source.`
- 
- An example of a source is the `location.search` property because it reads input from the query string, which is relatively simple for an attacker to control.
- This includes the referring URL (exposed by the document.referrer string), the user's cookies (exposed by the document.cookie string), and web messages.

### **A. List of Vulnerable Sources with Secure Alternatives**

| **Vulnerable Source**          | **Description**                              | **Example**                      | **Secure Alternative**               |
|--------------------------------|---------------------------------------------|----------------------------------|--------------------------------------|
| `location.href`                | Full URL of the current page.                | `location.href.split('#')[1]`   | Validate input before using it.    |
| `location.hash`                | Fragment identifier from the URL.           | `location.hash.substring(1)`    | `decodeURIComponent(location.hash)` with validation. |
| `location.search`              | Query string from the URL.                   | `location.search.split('=')[1]` | Use `URLSearchParams` to sanitize. |
| `document.URL`                 | Full URL of the document.                    | `document.URL`                  | Validate and sanitize URL.         |
| `document.documentURI`         | URI of the document.                         | `document.documentURI`          | Use `URL()` for safe parsing.      |
| `window.name`                  | Name of the window, can be modified.         | `window.name`                   | Sanitize `window.name` before use. |
| `localStorage.getItem()`        | Retrieves data stored in localStorage.       | `localStorage.getItem('key')`   | Validate and sanitize stored data. |
| `sessionStorage.getItem()`      | Retrieves data stored in sessionStorage.     | `sessionStorage.getItem('key')` | Validate and sanitize data.        |
| `XMLHttpRequest.responseText`  | Untrusted response data from XHR.            | `xhr.responseText`              | Parse JSON securely.               |
| `postMessage()`                | Receives untrusted messages.                 | `event.data`                    | Validate data and its origin.      |
| `element.innerText` / `.textContent` | Can be manipulated via JS.           | `element.innerText`             | Use `textContent` safely.          |

---

## 2. Sinks `JavaScript function or DOM object`
- A sink is a potentially dangerous JavaScript function or DOM object that can cause undesirable effects if attacker-controlled data is passed to it.
- The `point in the code where the untrusted data is used such as inserting the data into the DOM or executing it as JavaScript`.
- 
- For example, the `eval() function` is a sink because it processes the argument that is passed to it as JavaScript.
- An example of an HTML sink is `document.body.innerHTML` because it potentially allows an attacker to inject malicious HTML and execute arbitrary JavaScript.

### **B. List of Vulnerable Sinks with Secure Alternatives**

| **Vulnerable Sink**             | **Description**                              | **Example**                        | **Secure Alternative**              |
|---------------------------------|----------------------------------------------|------------------------------------|------------------------------------|
| `element.innerHTML`             | Injects HTML/JavaScript into an element.    | `div.innerHTML = userInput;`       | `element.textContent`              |
| `element.outerHTML`             | Replaces the entire element and content.    | `div.outerHTML = userInput;`       | `element.innerText`                |
| `document.write()` / `writeln()` | Writes content directly to the document.    | `document.write(userInput);`       | **Avoid Using It**                  |
| `element.insertAdjacentHTML()`  | Inserts HTML at a specific position.         | `div.insertAdjacentHTML('beforeend', userInput);` | Use `createElement()` and `appendChild()` |
| `eval()`                        | Executes arbitrary JavaScript code.         | `eval(userInput);`                 | Use `JSON.parse()` or `Function()` safely |
| `setTimeout()/setInterval()`    | Executes JS code after delay.                | `setTimeout(userInput, 1000);`     | Pass a **function, not a string** |
| `element.setAttribute()`        | Sets attributes on DOM elements.            | `a.setAttribute('href', userInput);` | Use strict whitelisting and encode input |
| `location.href` / `location.assign()` | Redirects to an untrusted URL.       | `location.href = userInput;`       | Validate URL before assignment    |
| `window.open()`                 | Opens a new window or tab.                   | `window.open(userInput);`          | Validate URL and use CSP policies |
| `element.style`                 | Injects untrusted styles, leading to CSS injection. | `div.style.cssText = userInput;` | Use `classList.add()` to apply safe styles |
---

## Taint-flow vulnerabilities: `Movement of untrusted data (tainted data) from a source (where the data enters the application) to a sink (where the data is used in a potentially dangerous way)`

## Taint Flow in DOM-Based XSS:

1. Source: `Data enters the application, often through URL parameters, user inputs, or other external data sources.`

2. Taint Propagation: The `data moves through the application's code, potentially passing through multiple variables and functions.`

3. Sink: `The data reaches a point where it is used in a way that can execute code`, such as by setting `innerHTML, eval(),` or other dangerous DOM properties and methods.

- Example:
```
<!DOCTYPE html>
<html>
<head>
    <title>User Profile</title>
</head>
<body>
    <h1 id="greeting">Welcome!</h1>
    <script src="script.js"></script>
</body>
</html>


JS:
// Source: User input from URL
const params = new URLSearchParams(window.location.search);
const user = params.get('user');

// Sink: Direct insertion into the DOM
document.getElementById('greeting').innerHTML = 'Welcome, ' + user + '!';
```

- Source: The data originates from the URL parameter user.
- Taint Propagation: The data is read from the URL and stored in the user variable.
- Sink: The data is directly inserted into the DOM using innerHTML.

> If an attacker crafts a URL like `https://example.com/profile.html?user=<script>alert('XSS');</script>`, the malicious script will be executed in the browser, leading to a DOM-based XSS attack.

## Preventing DOM-Based XSS:
- `Break the taint flow by ensuring that untrusted data is properly sanitized or validated before it reaches a sink`
```
const params = new URLSearchParams(window.location.search);
const user = params.get('user');
