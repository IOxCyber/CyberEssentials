[HTTP-Methods AKA HTTP-Verb](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- An HTTP method is 'SAFE' if it doesn't alter the state of the server. In other words, 'a method is safe if it leads to a read-only operation.' eg. GET, HEAD, or OPTIONS.
- An HTTP method is 'idempotent' if the intended effect on the server of making a single request is the same as the effect of making several identical requests. eg. common non-idempotent methods: POST, PATCH, CONNECT
> All safe methods are idempotent, as well as PUT and DELETE
- 'cacheable' response is an HTTP response that can be cached, that is stored to be retrieved and used later, saving a new request to the server. eg. common cacheable methods: GET, HEAD

> In practice, most APIs use GET, POST, PUT, PATCH, DELETE, and OPTIONS. CONNECT and TRACE are more relevant to network-level operations than typical API usage.

## Ports:
```
Port 80: For APIs using the HTTP protocol.
Port 443: For APIs using the HTTPS protocol.
Other custom ports: Some APIs may run on specific ports (e.g., microservices running on a custom port like 8080).
```

# Http-Headers in Details:
### **1. GET Request**
#### Request:
```http
GET /api/users/123 HTTP/1.1
Host: example.com
Accept: application/json
```

#### Response:
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 123,
  "name": "John Doe",
  "email": "john.doe@example.com"
}
```
- **Explanation**: The GET request retrieves data for the user with ID 123. The server returns a `200 OK` status with the user's data in JSON format.

---

### **2. HEAD Request**
#### Request:
```http
HEAD /api/users/123 HTTP/1.1
Host: example.com
```

#### Response:
```http
HTTP/1.1 200 OK
Content-Type: application/json
```
- **Explanation**: The HEAD request retrieves the headers of the GET request without the body content. The server confirms that the resource exists with a `200 OK` status.

---

### **3. POST Request**
#### Request:
```http
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "Jane Doe",
  "email": "jane.doe@example.com"
}
```

#### Response:
```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "id": 124,
  "name": "Jane Doe",
  "email": "jane.doe@example.com"
}
```
- **Explanation**: The POST request submits data to create a new user. The server responds with a `201 Created` status, and the newly created resource with an ID is returned.

---

### **4. PUT Request**
#### Request:
```http
PUT /api/users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "name": "John Smith",
  "email": "john.smith@example.com"
}
```

#### Response:
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 123,
  "name": "John Smith",
  "email": "john.smith@example.com"
}
```
- **Explanation**: The PUT request updates the entire user resource. The server responds with a `200 OK` status and the updated resource data.

---

### **5. DELETE Request**
#### Request:
```http
DELETE /api/users/123 HTTP/1.1
Host: example.com
```

#### Response:
```http
HTTP/1.1 204 No Content
```
- **Explanation**: The DELETE request removes the user with ID 123. The server responds with a `204 No Content` status, indicating that the deletion was successful, and no further content is returned.

---

### **6. CONNECT Request**
#### Request:
```http
CONNECT example.com:443 HTTP/1.1
Host: example.com
```

#### Response:
```http
HTTP/1.1 200 Connection Established
```
- **Explanation**: The CONNECT request is used to establish a tunnel, often for HTTPS traffic. The server responds with `200 Connection Established`.

---

### **7. OPTIONS Request**
#### Request:
```http
OPTIONS /api/users HTTP/1.1
Host: example.com
```

#### Response:
```http
HTTP/1.1 204 No Content
Allow: GET, POST, OPTIONS
```
- **Explanation**: The OPTIONS request asks for the allowed methods on a resource. The server responds with a `204 No Content` status and the `Allow` header lists the supported HTTP methods (`GET`, `POST`, `OPTIONS`).

---

### **8. TRACE Request**
#### Request:
```http
TRACE /api/users HTTP/1.1
Host: example.com
```

#### Response:
```http
HTTP/1.1 200 OK
Content-Type: message/http

TRACE /api/users HTTP/1.1
Host: example.com
```
- **Explanation**: The TRACE request is echoed back by the server. This response can be used to troubleshoot or trace how the request is processed.

---

### **9. PATCH Request**
#### Request:
```http
PATCH /api/users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
  "email": "john.newemail@example.com"
}
```

#### Response:
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 123,
  "name": "John Smith",
  "email": "john.newemail@example.com"
}
```
- **Explanation**: The PATCH request partially updates the resource (in this case, only the email field). The server responds with a `200 OK` status and the updated resource data.

---

