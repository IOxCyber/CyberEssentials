# Broken Access Control `Prevention Techniques`

## 1. **Never rely on obfuscation alone for access control**
   - Always use proper access control mechanisms rather than just hiding links or files.

## 2. **Deny access by default**
   - Assume everything is private and explicitly make resources public if necessary.

## 3. **Use a single application-wide mechanism**
   - Enforce access controls consistently throughout your application using a unified approach.

## 4. **Mandatory declarations of access at the code level**
   - Developers should explicitly declare access permissions for each resource.

## 5. **Audit and test access controls**
   - Regularly review and test your access control mechanisms to ensure they are effective.

## 6. CORS (Cross-Origin Resource Sharing):
   - A security feature implemented by web browsers `to prevent web pages from requesting a different domain` than the one that served the web page.
   - The `browser sends a preflight request (an HTTP OPTIONS request) to the server to check if the cross-origin request is allowed.`
   - The server responds with the allowed methods, headers, and origins. If the server approves the request, the browser makes the actual request.
   - eg. `website running on https://example.com and you want to make a request to an API hosted on https://api.example.com.`

```
Eg.
Server Response Header (Secure):

Access-Control-Allow-Origin: https://example.com
Access-Control-Allow-Methods: GET, POST
Access-Control-Allow-Headers: Content-Type

Server Response Header (Vuln):
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, POST, PUT, DELETE
Access-Control-Allow-Headers: Content-Type
```
