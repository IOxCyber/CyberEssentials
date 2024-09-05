[HTTP-Methods AKA HTTP-Verb](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- An HTTP method is 'SAFE' if it doesn't alter the state of the server. In other words, 'a method is safe if it leads to a read-only operation.' eg. GET, HEAD, or OPTIONS.
- An HTTP method is 'idempotent' if the intended effect on the server of making a single request is the same as the effect of making several identical requests. eg. common non-idempotent methods: POST, PATCH, CONNECT
> All safe methods are idempotent, as well as PUT and DELETE
- 'cacheable' response is an HTTP response that can be cached, that is stored to be retrieved and used later, saving a new request to the server. eg. common cacheable methods: GET, HEAD


1. Lab: Exploiting an API endpoint using documentation: [Link](https://portswigger.net/web-security/api-testing/lab-exploiting-api-endpoint-using-documentation)
- Update the email > In Proxy > HTTP history, right-click the `PATCH /api/user/wiener` request and select Send to Repeater.
> The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
- Find the documentation: `GET /api/ HTTP/2`
- Delete the user: `DELETE /api/user/carlos HTTP/2`


2. [Finding and exploiting an unused API endpoint](https://portswigger.net/web-security/api-testing/lab-exploiting-unused-api-endpoint)
- Update the email > In Proxy > HTTP history, right-click the `GET /api/products/4/price HTTP/2` request and select Send to Repeater.
> The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
- Change the Method: `PATCH /api/products/1/price HTTP/2` > `"error":"Only 'application/json' Content-Type is supported"`
- Add `Content-Type: application/json` & {"price": 0} in body
- It will update the Price in the Application.
- ![image](https://github.com/user-attachments/assets/2131ee78-052c-417f-b043-c6b6e9b93d09)


