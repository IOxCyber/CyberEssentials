## CASB (Cloud Application Security Broker):
Security policy enforcement point, placed between cloud service consumers and providers.
CASB monitors the overall cloud usage.
Secures cloud data in motion (via proxy) and at rest (via APIs).
Example security policies include authentication, single sign-on, authorization, credential mapping, device profiling, encryption, tokenization, logging, alerting, malware detection/prevention

## SASE (Secure access service edge): sassy
A framework for network security architecture that brings cloud native security technologies with wide area network (WAN) 
Provides capabilities to securely connect users, systems, and endpoints to applications and services anywhere. 

## Cloud native security technologies: SWG, CASB, ZTNA, and FWaaS.
The “edge” in SASE refers to the cloud provider’s global systems.

## SASE vs CNAPP:
SASE consolidates all network security functions and network functions by providing single-pane-of-glass for network security policy management & observability. 
CNAPP consolidates all cloud security functions under one umbrella.

SD-WAN: a software-defined approach to managing the WAN, subs to MPLS

MPLS (Multi- Protocol Label Switching): a private connection linking data centers and branch offices.

Firewall as a service (FWaaS): a network security technology referring to a cloud firewall that delivers advanced Layer 7/next-generation firewall (NGFW) capabilities, including access controls, such as URL filtering, advanced threat prevention, intrusion prevention systems (IPS), and DNS security.

Cloud SWG: secure web gateway that helps you secure egress web traffic (HTTP/S).
identifies traffic that doesn't conform to policy and logs it to Cloud Logging (Logging). 
control the flow of data between your network and the internet at the application level.

SWG vs Firewall:
WAFs also inspect traffic, but at the packet level, using deep packet inspection rules to identify safe applications.


Zero Trust Network Access (ZTNA): an IT security solution/ security frameworks that provides secure remote access to an organization's applications, data, and services based on clearly defined access control policies.

ZTNA vs VPN:
VPNs route traffic through multiple servers and then through a central point in the corporate data center, which can cause latency in the connection but ZTNA provide direct access w/o latency.


NGFW firewall:
A part of the 3rd generation of firewall technology with in-line deep packet inspection, IDS system.

IPsec: IP security 
framework of related security protocols that secure communications at the network or packet processing layer.
