# Prerequisites:
1. Client Approval and Scope:
- Written `approval from the client, Scope of the assessment` clearly (e.g., specific subdomains, parts of the site).
- Testing type: Any One of [BlackBox(Only URL), WhiteBox(Access/Access Validation), GreyBox.

2. Setup Environment:
- `Configure Burp Suite and your browser to intercept traffic`

3. Objectives & Duration:
- Create a testing plan that outlines the objectives, timeline, and reporting format.

4. Info Gathering:
- Collect relevant information about the site, such as domain details, technologies used, and any login credentials if provided.

# Steps:
1. Reconnaissance and Information Gathering:
- Initial Recon: Use tools like `whois and nslookup to gather domain and IP information`.
- Subdomain Enumeration: Use `sublist3r to find subdomains.`
- Spider the Website: Use `Burp Suite’s Spider tool to map out the website structure.`
- Proxy Interception: Navigate through the site while Burp Suite's `Proxy is intercepting traffic to capture requests and responses.`
- Identify Technologies: `Look for HTTP headers, JavaScript files, and other indicators to determine the technologies in use.`

2. Vulnerability Scanning: Or Manually Find the Vulnerabilities (Step 3)
- Active Scan: Use Burp Suite’s `Scanner to scan the entire site for common vulnerabilities.`
- Review Findings: `Examine the scanner results to identify high-risk vulnerabilities such as SQL injection, XSS, CSRF, etc.`

3.  Manual Testing
Tools: Burp Suite (Repeater, Intruder, Proxy, Decoder, Comparer)

4. Reporting:
- Document Findings (How the vul found and steps to mitigate it)
- Provide the Reports (from Tool)
- Present findings (Walkthrough the findings & recommonded Actions)

