## 1. Input validation by applying apply the allowlist/Whitelisting approach, regex.
```
The request sent to the internal application will be based on the following information:

String containing business data.
IP address (V4 or V6).
Domain name.
URL.

//Regex validation for a data having a simple format
if(Pattern.matches("[a-zA-Z0-9\\s\\-]{1,50}", userInput)){
    //Continue the processing because the input data is valid
}else{
    //Stop the processing and reject the request
}
```

## 2. Network segregation is highly recommended in order to block illegitimate calls directly at network level itself.
![image](https://github.com/user-attachments/assets/6f661491-893a-481f-95cc-2649ee25ebae)


## 3.  Disable Unnecessary URL Schemes:
Ensure that the application only processes necessary URL schemes (e.g., http, https). Block dangerous schemes like file://, ftp://, gopher://, or data://, which can be abused to access local files or perform other malicious actions.

> Note: Disable the support for the following of the redirection in your web client in order to prevent the bypass of the input validation

## 4. Enforce DNS Resolution Rules
Resolve DNS locally: When resolving hostnames, ensure DNS resolution is performed on trusted DNS servers and reject any lookups that resolve to private IP ranges.
Avoid untrusted DNS services: Ensure that the server does not rely on external or untrusted DNS servers that may return malicious IP addresses.

## 5. Limit Outbound Traffic
Restrict outbound requests: Configure servers to limit the number and destination of outgoing requests.

## 6. Use Web Application Firewalls (WAF)
A WAF can help block common SSRF attacks by detecting and filtering malicious patterns, such as requests to internal services or suspicious URLs.

| **Prevention Method**                   | **Description**                                                                                               |
|-----------------------------------------|---------------------------------------------------------------------------------------------------------------|
| **Input Validation**                    | Sanitize and validate URLs/IPs, reject dangerous inputs, and allow only whitelisted domains/IPs.               |
| **Disable Unnecessary URL Schemes**     | Only allow HTTP/HTTPS requests, block `file://`, `ftp://`, `gopher://`, and other potentially dangerous schemes.|
| **DNS Resolution Rules**                | Ensure safe DNS resolution by blocking private IP ranges and avoiding untrusted DNS servers.                   |
| **Network Firewall Rules**              | Implement network-level protections to block requests to internal services or private IP ranges.               |
| **Cloud Metadata Service Protection**   | Protect cloud environments by blocking or restricting access to metadata services like AWS `169.254.169.254`.   |
| **Limit Outbound Traffic**              | Restrict outbound requests using network egress controls to only approved destinations.                        |
| **Use WAF**                             | Deploy a Web Application Firewall (WAF) to filter and detect SSRF attacks.                                     |
| **Monitoring and Logging**              | Monitor and log outgoing requests, and set up alerts for unusual behavior.                                     |
| **Service Isolation**                   | Isolate sensitive services from public-facing endpoints by using network segmentation or reverse proxies.      |
