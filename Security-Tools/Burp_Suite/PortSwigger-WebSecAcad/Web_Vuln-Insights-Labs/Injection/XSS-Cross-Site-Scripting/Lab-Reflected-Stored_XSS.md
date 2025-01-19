[Cheatsheet](https://portswigger.net/web-security/cross-site-scripting/cheat-sheet)


# Reflected:
## Lab 1. Reflected XSS into HTML context with nothing encoded [link](https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded)
- Injection: `<script>alert(1)</script>` in Search field


# Stored:
## Lab 2. Stored XSS into HTML context with nothing encoded [link](https://portswigger.net/web-security/cross-site-scripting/stored/lab-html-context-nothing-encoded)
- Injection: `<script>alert(1)</script>` in Comment Section
- Fill out other details & submit
- Everytime the page reloads, the user will get a `alert 123`
