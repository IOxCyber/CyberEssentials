1. CVE: Common Vulnerability & Exposure (`DB of all publically known Vuln`)
2. CVSS: Common Vulnerability Scoring System `Low (0.1 - 3.9) < Medium (4.0 - 6.9) < High (7.0 - 8.9) < Critical (9.0-10)`
3. CVSS Types: Base (Actual), Temporal (Varties with times & Events), Environmental (Specific to Organization)
4. Vuln Levels: `Red (Confirmed) > Yellow (Potential) > Blue (Information Gathered)`
5. Log Location {`Linux: var/log/qualus`}, Windows {`C/programData/qualys`}: Hidden

---
---

6. Maps: Network/Asset Discovery & Visualization tool
7. False Positive: Eg. Misidentification of Unpatched s/w versions, Default Config detection, Open Ports/SSL Misconfig.
8. False Negative: Eg. Unpatch Vuln, Misconfig firewall Rules, WebApp Vuln (SQLi)
9. EDR: Endpoint Detection & Response (`For individual Endpoints, Monitoring & Responding to threats`) eg. MS Defender, SentinelOne
10. XDR: Extended Detection & Response (`Integrates & correlates data from multiple security tools`) eg. MS 365 Defender, Palo Alto Cortex XDR

---
---

11. PoC: `Proof of Concept` (How a vuln can be exploited)
12. Zero Day Vuln: `Vuln discovered & exploitable by the attackers before the patch are released` eg. XSS, SQLi, Remote Code Execution (Log4j, SMBv1) etc
13. DNS: Domain Name System eg. `Scheme://SubDomain.Domain.Top-Level-Domain:Port/Query?` https://www.example.com:443/Search?
14. To check listening Ports: `Win > netstat -an | find "Listen"` `Linux > netstat -tuln (Self)`, nmap -p 443 IP_Addr (Other IP), nc -vz IP_Addr 80
15. 
16. 
17.

---
---

