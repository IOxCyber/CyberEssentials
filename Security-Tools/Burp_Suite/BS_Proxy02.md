# Burp Proxy:
- `To capture requests and responses(Inactive by default) between our host and target machine.`
- These requests can then be manipulated or sent to other modules for further processing before being allowed to continue to their destination.

- This ability to intercept requests ultimately means that we can take complete control over our web traffic.

- We can click the `Intercept is on` button to disable the Intercept, which will allow requests to pass through the proxy without being stopped.

- The WebSocket communication logs can be viewed by going to the "HTTP history" and "WebSockets history" sub-tabs.

- Any requests captured here can be **sent to other tools** in the framework by right-clicking them and choosing "Send to...".

- The **proxy will not intercept server responses by default** unless we explicitly ask it to on a per-request basis. We can **override the default setting by selecting the "Intercept responses based on the following rules" checkbox** and picking one or more rules. The "Or Request Was Intercepted" rule is good for catching responses to all requests that were intercepted by the proxy.

## FoxyProxy (Connecting through the proxy):
- Two ways to proxy our traffic through Burp Suite i.e Using embedded browser & configure Local web browser to proxy the traffic through Burp.

- Burp `Proxy works by opening a web interface on 127.0.0.1:8080 (by default)`, we need to redirect all of our browser traffic through this port before we can start intercepting it with Burp. It can be done by using **FoxyProxy**.

- There are two versions of FoxyProxy: Basic and Standard. Both versions allow you to change your proxy settings on the fly.

## Scoping and Targeting:
- Setting a scope for the project allows us to define what gets proxied and logged. Target tab > right-clicking our target from our list on the left, then choosing "Add To Scope".

- Scope allows us to control Burp's target scope for the project. 








