## Stored-XSS:
- Arises when an application receives data from an untrusted source and includes that data within its later HTTP responses in an unsafe way.

## Example:
```
This allows users to submit comments on blog posts, which are displayed to other users

POST /post/comment HTTP/1.1
Host: vulnerable-website.com
Content-Length: 100

postId=3&comment=This+post+was+extremely+helpful.&name=Carlos+Montoya&email=carlos%40normal-user.net


After this comment has been submitted, any user who visits the blog post will receive the following within the application's response:
<p>This post was extremely helpful.</p>
```
- An attacker can inject the JS code `<script>/* Bad stuff here... */</script>` in Comments
- Encoded it as `comment=%3Cscript%3E%2F*%2BBad%2Bstuff%2Bhere...%2B*%2F%3C%2Fscript%3E`
- Any user who visits the blog post will now receive the following within the application's response: `<p><script>/* Bad stuff here... */</script></p>`


## Test for stored XSS vulnerabilities:
- `Entry points into the application's processing` include:
- Parameters or other data within the URL query string and message body.
- The URL file path.
- HTTP request headers that might not be exploitable in relation to reflected XSS.
- Any out-of-band routes via which an attacker can deliver data into the application.



