# Preventing CORS-Based Attacks

Cross-Origin Resource Sharing (CORS) vulnerabilities typically arise from misconfigurations. As such, prevention largely involves correct configuration. Below are key strategies for defending against CORS attacks:

## 1. Proper Configuration of Cross-Origin Requests

Ensure that the `Access-Control-Allow-Origin` header is correctly configured to specify only trusted origins, especially when dealing with sensitive information.

## 2. Only Allow Trusted Sites

**Avoid**: Specifying origins in the `Access-Control-Allow-Origin` header that are not trusted. Be cautious of dynamically reflecting origins from cross-origin requests without proper validation, as this can be easily exploited.

## 3. Avoid Whitelisting `null`

**Avoid**: Using `Access-Control-Allow-Origin: null`. This setting allows cross-origin resource calls from internal documents and sandboxed requests, which can specify the null origin. Define CORS headers with respect to trusted origins for both private and public servers.

## 4. Avoid Wildcards in Internal Networks

**Avoid**: Using wildcards in internal network configurations. Relying solely on network security to protect internal resources is inadequate when internal browsers may access untrusted external domains.

## 5. CORS is Not a Substitute for Server-Side Security Policies

**Important**: CORS governs browser behavior and should not replace server-side protections for sensitive data. An attacker can forge requests from any trusted origin. Ensure that web servers enforce additional security measures, such as authentication and session management, alongside properly configured CORS.

---
