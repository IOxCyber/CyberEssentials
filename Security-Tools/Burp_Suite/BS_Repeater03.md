# Repeater: (To Modify requests)
- `Repeater allows us to craft and/or relay intercepted requests to a target at will.`
- can take a request captured in the Proxy, edit it, and send the same request repeatedly as many times as required.
- With a request captured in the proxy, we can send to repeater either by right-clicking on the request and choosing "Send to Repeater" or by pressing Ctrl + R.
- It'll show **Target** & **Inspector** (All the site elements).
- **Render** option displays the response in the same format as your browser would display.

## Response & View
- Four display Options:
1. Pretty: This is the default option. It takes the raw response and attempts to beautify it slightly, making it easier to read.
2. Raw: The pure, un-beautified response from the server.
3. Hex: This view takes the raw response and gives us a byte view of it -- especially useful if the response is a binary file.
4. Render: The **render view renders the page as it would appear in your browser**. Whilst not hugely useful given that we would usually be interested in the source code when using Repeater, this is still a neat trick.

## Inspector:
- Used in request and response fields of the Repeater, gives us a list of the components in the request and response.
- Inspector can be used in the Proxy as well as Repeater.

## other sections available for viewing and/or editing:
- Query Parameters, which refer to data being sent to the server in the URL for GET method[^1].
- Body Parameters, which do the same thing as Query Parameters, but for POST requests[^2].
- Request Cookies contain, as you may expect, a modifiable list of the cookies which are being sent with each request.
- Request Headers allow us to view, access, and modify (including outright adding or removing) any of the headers being sent with our requests. 
- Response Headers show us the headers that the server sent back in response to our request, not editable.


## SQLi with Repeater:
- Adding (') at ID will give an idea about vulnerability of SQLi & cause "500 Internal Server Error"
- By setting the ID to an invalid number, we  ensure that we don't retrieve anything with the original (legitimate) query.









[^1]: GET carries request parameter appended in URL string while POST carries request parameter in message body.
[^2]: Both GET and POST method is used to transfer data from client to server in HTTP protocol.
