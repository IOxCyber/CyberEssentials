## SSL-TLS-Handshaking: [More](https://www.cloudflare.com/en-gb/learning/ssl/what-happens-in-a-tls-handshake/) `To establish a secure & encrypted connection between a client & Server using HTTPs`

## When it happens:
- Takes place whenever a user navigates to a `website over HTTPS` and the browser first begins to query the website's origin server.
- Also happens whenever any other `communications use HTTPS, including API calls and DNS over HTTPS queries.`

> Note: TLS handshakes occur after a TCP connection has been opened via a TCP handshake.

## What happens during Handshaking:
- 1. What `Version of TLS (TLS 1.0, 1.2, 1.3, etc.)` will be used.
- 2. What `Cipher Suites eg. TLS_RSA_WITH_AES_128_GCM_SHA256` (RSA: key exchange and authentication algorithm, AES: encryption algorithm for Data using a 128–bit key, SHA256: MAC algorithm for hashing/Data Integrity) will be used.
- 3. `Authenticate the identity of the server` via the server’s public key and the SSL certificate authority’s digital signature.
- 4. `Generate session keys` to use symmetric encryption after the handshake is complete.

- ![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/82c9ecbb-92cb-471d-9b85-26fbec1aba89)

## When to Use:
- can be used with any protocol that uses TCP as the transport layer.

> Pre-Shared Key: Both the client and server possess a shared secret key (pre-shared key). This key is used directly for key exchange, eliminating the need for public-key cryptography.
> The public key is shared openly, while the private key is kept secure. The public key is included in the digital certificate.
