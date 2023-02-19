## Burp: Repeater: (To Modify requests)
- Repeater allows us to craft and/or relay intercepted requests to a target at will.
- can take a request captured in the Proxy, edit it, and send the same request repeatedly as many times as we wish.
- With a request captured in the proxy, we can send to repeater either by right-clicking on the request and choosing "Send to Repeater" or by pressing Ctrl + R.
- It'll show **Target** & **Inspector** (All the site elements).
- **Render** option displays the response in the same format as your browser would display.


## Response
- Four display Options:
1. Pretty: This is the default option. It takes the raw response and attempts to beautify it slightly, making it easier to read.
2. Raw: The pure, un-beautified response from the server.
3. Hex: This view takes the raw response and gives us a byte view of it -- especially useful if the response is a binary file.
4. Render: The **render view renders the page as it would appear in your browser**. Whilst not hugely useful given that we would usually be interested in the source code when using Repeater, this is still a neat trick.

