# 'Arises when an application receives data in an HTTP request and includes that data within the immediate response`

```
Suppose a website has a search function which receives the user-supplied search term in a URL parameter:
https://insecure-website.com/search?term=gift

The application echoes the supplied search term in the response to this URL:
<p>You searched for: gift</p>

Assuming the application doesn't perform any other processing of the data, an attacker can construct an attack like this:
https://insecure-website.com/search?term=<script>/*+Bad+stuff+here...+*/</script>

This URL results in the following response:
<p>You searched for: <script>/* Bad stuff here... */</script></p>
```

## Reflected XSS in different contexts:
- There are many different varieties of reflected cross-site scripting.
- The location of the reflected data within the application's response determines what type of payload is required to exploit it and might also affect the impact of the vulnerability.

## How to find and test for reflected XSS vulnerabilities:
1. `Test every entry point.` Test separately every entry point for data within the application's HTTP requests. This includes parameters or other data within the URL query string and message body, and the URL file path. It also includes HTTP headers, although XSS-like behavior that can only be triggered via certain HTTP headers may not be exploitable in practice.
2. `Submit random alphanumeric values.` For each entry point, submit a unique random value and determine whether the value is reflected in the response. The value should be designed to survive most input validation, so needs to be fairly short and contain only alphanumeric characters
3. `Determine the reflection context`. For each location within the response where the random value is reflected, determine its context. This might be in text between HTML tags, within a tag attribute which might be quoted, within a JavaScript string, etc.
4. `Test a candidate payload`. Based on the context of the reflection, test an initial candidate XSS payload that will trigger JavaScript execution if it is reflected unmodified within the response


## Impact of reflected XSS attacks:
- If an attacker can control a script that is executed in the victim's browser, then they can typically fully compromise that user.
- Amongst other things, the attacker can:
```
Perform any action within the application that the user can perform.
View any information that the user is able to view.
Modify any information that the user is able to modify.
Initiate interactions with other application users, including malicious attacks, that will appear to originate from the initial victim user.
```

