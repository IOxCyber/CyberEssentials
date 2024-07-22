# Client-Side Vulnerability [Cheatsheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)

## Cross-site scripting (XSS):
-  Allow an attacker to masquerade as a victim user, to carry out any actions that the user can perform, and to access any of the user's data.

## Impact:
- An attacker who exploits a cross-site scripting vulnerability is typically able to:
```
Impersonate or masquerade as the victim user.
Carry out any action that the user is able to perform.
Read any data that the user is able to access.
Capture the user's login credentials.
Perform virtual defacement of the web site.
Inject trojan functionality into the web site.
```

## 3 main types of XSS attacks

### 1. Reflected XSS
- where the malicious script `comes from the current HTTP request.`
- It arises `when an application receives data in an HTTP request and includes that data within the immediate response` in an unsafe way.
- simplest variety of cross-site scripting.
- eg. `https://insecure-website.com/status?message=All+is+well.<p>Status: All is well.</p>`

### 2. Stored XSS
- where the malicious script `comes from the website's database.`
- AKA persistent or second-order XSS.
- It arises `when an application receives data from an untrusted source and includes that data within its later HTTP responses` in an unsafe way.
- for example, comments on a blog post, user nicknames in a chat room, or contact details on a customer order, a webmail application displaying messages received over SMTP, a marketing application displaying social media posts, or a network monitoring application displaying packet data from network traffic.
- eg. `<p>Hello, this is my message!</p>`

### 3. DOM-based XSS
-  `where the vulnerability exists in client-side code rather than server-side code.`
- DOM-based vulnerabilities arise `when a website contains JavaScript that takes an attacker-controllable value, known as a source, and passes it into a dangerous function, known as a sink.`
- Craft a DOM-based JS code > Distribute to User > Execute Code

> the most effective way to avoid DOM-based vulnerabilities is to avoid allowing data from any untrusted source to dynamically alter the value that is transmitted to any sink.

---
---

### Source & Sink:

## 1. Sources `Value/Data`
- A source is a JavaScript property that accepts data that is potentially attacker-controlled.
- This could be `user input, URL parameters, or any other data coming from an external or untrusted source.`
- Ultimately, `any property that an attacker can control is a potential source.`
- 
- An example of a source is the `location.search` property because it reads input from the query string, which is relatively simple for an attacker to control.
- This includes the referring URL (exposed by the document.referrer string), the user's cookies (exposed by the document.cookie string), and web messages.
```
document.URL
document.documentURI
document.URLUnencoded
document.baseURI
location
document.cookie
document.referrer
window.name
history.pushState
history.replaceState
localStorage
sessionStorage
IndexedDB (mozIndexedDB, webkitIndexedDB, msIndexedDB)
Database
```

## 2. Sinks `JavaScript function or DOM object`
- A sink is a potentially dangerous JavaScript function or DOM object that can cause undesirable effects if attacker-controlled data is passed to it.
- The `point in the code where the untrusted data is used such as inserting the data into the DOM or executing it as JavaScript`.
- 
- For example, the `eval() function` is a sink because it processes the argument that is passed to it as JavaScript.
- An example of an HTML sink is `document.body.innerHTML` because it potentially allows an attacker to inject malicious HTML and execute arbitrary JavaScript.
```

DOM-based vulnerability	Example sink
DOM XSS LABS	          document.write()
Open redirection LABS	  window.location
Cookie manipulation LABS	    document.cookie
JavaScript injection	        eval()
Document-domain manipulation	document.domain
WebSocket-URL poisoning	      WebSocket()
Link manipulation	            element.src
Web message manipulation	    postMessage()
Ajax request-header manipulation	setRequestHeader()
Local file-path manipulation	    FileReader.readAsText()
Client-side SQL injection	        ExecuteSql()
HTML5-storage manipulation	      sessionStorage.setItem()
Client-side XPath injection      	document.evaluate()
Client-side JSON injection	      JSON.parse()
DOM-data manipulation	            element.setAttribute()
Denial of service	                RegExp()
```

---
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

// Use textContent instead of innerHTML to avoid interpreting HTML
document.getElementById('greeting').textContent = 'Welcome, ' + user + '!';
```
- `textContent` ensures that any user `input is treated as plain text and not HTML` code.


