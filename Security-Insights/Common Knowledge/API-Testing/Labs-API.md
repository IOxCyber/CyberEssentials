[HTTP-Methods*](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

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


