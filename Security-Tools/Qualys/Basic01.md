## Vulnerability Management Life Cycle::
1. Discovery: Discovery is the first step of VM life cycle. It is the process of discovering assets present within the network.
2. Organize Assets: In this phase, assets are organized into different groups depending on various factors, which includes their risk factor and threat impact.
3. Assess: After organizing the assets, assess helps an administrator to perform vulnerability scans to find any vulnerabilities that might result in a security breach.
4. Report: Based on the discovered vulnerable assets, administrators can generate reports to prioritize the identified vulnerabilities, based on their impact.
5. Remediate: Depending on their risk factor and threat impact, remediation plans could be created and implemented.
6. Verify: This phase of the VM lifecycle checks if remediation actions were successful to what extent. 

# <> Discovery > Organize Assets > Assess > Report > Remediate > Verify <>

## Scans:
- We can perform Discovery, vulnerability, and compliance scans.
- Here’s a list of devices that can be scanned: all routers, switches, hubs, firewalls, servers (all common operating systems), workstations, databases, desktop computers, printers, and wireless access devices.
- Vulnerability range including back doors and trojan horses, brute force attacks, CGI, databases, DNS and Bind, e-commerce applications, file sharing, FTP, firewalls, General Remote Services, hardware and network appliances, mail services, SMB/Netbios Windows, TCP/IP, VMware, VoIP, web servers, wireless access points, X-windows & more.

> Not sure what you have? Run a discovery scan (map) to find the live devices on your network.

### Asset groups: [I'm here](https://docs.qualys.com/en/vm/10.29.0.0/asset_groups/win_asset_group.htm)
- `User-defined groupings of host assets (IP addresses).`
- You can group hosts by importance, priority, location, ownership, or any other method that makes sense for your organization.
- Only the hosts in the group are scanned when you scan an asset group.

### Asset tagging: [I'm here](https://docs.qualys.com/en/vm/10.29.0.0/host_assets/tags_asset_tagging.htm)
- Another method for organizing and tracking the assets in your account.
- You can assign tags to your host assets, can select when set up a scan.
- This dynamic approach is a great way to ensure you include all hosts that match certain criteria, even if your network is constantly changing as hosts are added and removed. 

## FAQs:
- Can we scan an asset group with a mix of external and internal IP addresses `NO`
- A scan is automatically `canceled after 4 hours if it remains in queued` status due to platform issues.
- Qualys Cloud Agent scan executes every four hours ie 240 mins.
- External scanning is always available using our cloud scanners set up around the globe at our Security Operations Centers (SOCs). `External from the Scanner Appliance menu`.
- Internal scanning uses scanner appliances placed inside your network. Choose the "Build my list" option to select one or more scanner appliances for your scan task





