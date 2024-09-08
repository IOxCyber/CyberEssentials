# SSRF: Server Side Request Forgery
- Vulnerability `that allows an attacker to cause the server-side application to make requests to an unintended location.`
- Unintended locations such as arbitrary external systems or Internal resources.
- SSRF is an attack vector that abuses an application to interact with the internal/external network or the machine itself.

[![image](https://github.com/user-attachments/assets/9ecfb8e1-6da4-4749-bfad-046367e2f98b)](https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet.html#overview-of-a-ssrf-common-flow)

> If the application is vulnerable to XML eXternal Entity (XXE) injection then it can be exploited to perform a SSRF attack.

# Common SSRF attacks:
- SSRF attacks often `exploit trust relationships to escalate` an attack from the vulnerable application and perform unauthorized actions.
- These trust relationships might exist in `relation to the server, or in relation to other back-end systems` within the same organization.
- The client requests can have 2 cases after reaching to Server:
  1. Querying the Internal Resource.
  2. Requesting to the Outside Resource.
