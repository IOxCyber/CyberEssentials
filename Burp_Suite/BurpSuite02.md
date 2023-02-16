# Burp Proxy:
- It allows us to capture requests and responses(Inactive by default) between our host and target machine. These request can then be manipulated or sent to other tools for further processing before being allowed to continue to their destination.

- This ability to intercept requests ultimately means that we can take complete control over our web traffic.

- We can click the **"Intercept is on" button to disable the Intercept**, which will allow requests to pass through the proxy without being stopped.

- The WebSocket communication logs can be viewed by going to the "HTTP history" and "WebSockets history" sub-tabs.

- Any requests captured here can be **sent to other tools** in the framework by right-clicking them and choosing "Send to...".

- The **proxy will not intercept server responses by default** unless we explicitly ask it to on a per-request basis. We can **override the default setting by selecting the "Intercept responses based on the following rules" checkbox** and picking one or more rules. The "Or Request Was Intercepted" rule is good for catching responses to all requests that were intercepted by the proxy.

## FoxyProxy (Connecting through the proxy):
- Two ways to proxy our traffic through Burp Suite i.e Using embedded browser & configure Local web browser to proxy the traffic through Burp.

- Burp Proxy works by opening a web interface on 127.0.0.1:8080 (by default), we need to redirect all of our browser traffic through this port before we can start intercepting it with Burp. It can be done by using **FoxyProxy**.

-  
