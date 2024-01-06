## SSL-TLS-Handshaking: [More](https://www.cloudflare.com/en-gb/learning/ssl/what-happens-in-a-tls-handshake/)

- ![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/82c9ecbb-92cb-471d-9b85-26fbec1aba89)

## When:
- A TLS handshake takes place whenever a user navigates to a website over HTTPS and the browser first begins to query the website's origin server.
- A TLS handshake also happens whenever any other communications use HTTPS, including API calls and DNS over HTTPS queries.

> Note: TLS handshakes occur after a TCP connection has been opened via a TCP handshake.

## What happens during Handshaking:
- 1. Specify which `version of TLS (TLS 1.0, 1.2, 1.3, etc.)`
- 2. Decide `cipher suites`
- 3. `Authenticate the identity of the server` via the server’s public key and the SSL certificate authority’s digital signature.
- 4. `Generate session keys` to use symmetric encryption after the handshake is complete.
