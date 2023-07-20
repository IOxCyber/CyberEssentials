# Att&ck: Adversarial Tactic, Techniques and common knowledge: [Official Site](https://attack.mitre.org/versions/v12/#)

- Knowledge base and model for cyber adversary behavior, reflecting the various phases of an adversary's attack lifecycle.
- Used worldwide across multiple disciplines including intrusion detection, threat hunting, security engineering, threat intelligence, red teaming, and risk management to improve their defenses.

## Core Components:
- `Matrices`: ATT&CK has matrices for different platforms and domains, enabling organizations to focus on the specific threats relevant to their environment.
- `Tactics`: Each matrix contains several tactics that represent the adversary's goals. Common tactics include Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Credential Access, Discovery, Lateral Movement, Collection, Exfiltration, and Impact.
- `Techniques`: Within each tactic, ATT&CK provides a list of specific techniques that adversaries use to accomplish their goals eg. "Phishing," "Remote Service Exploitation," or "Execution through API."
- `Procedures`: ATT&CK documents real-world examples of procedures, which are specific implementations or incidents where adversaries used that technique.
- `Mitigations`: ATT&CK provides guidance on mitigations and defensive strategies that organizations can employ to protect against each technique.

## MITRE ATT&CK Matrix: (General Overview)
1. Reconnaissance: gathering information to plan future adversary operations, i.e., information about the target organization
2. Resource Development: establishing resources to support operations, i.e., setting up command and control infrastructure
3. Initial Access: trying to get into your network, i.e., spear phishing
4. Execution: trying the run malicious code, i.e., running a remote access tool
5. Persistence: trying to maintain their foothold, i.e., changing configurations
6. Privilege Escalation: trying to gain higher-level permissions, i.e., leveraging a vulnerability to elevate access
7. Defense Evasion: trying to avoid being detected, i.e., using trusted processes to hide malware
8. Credential Access: stealing accounts names and passwords, i.e., keylogging
9. Discovery: trying to figure out your environment, i.e., exploring what they can control
10. Lateral Movement: moving through your environment, i.e., using legitimate credentials to pivot through multiple systems
11. Collection: gathering data of interest to the adversary goal, i.e., accessing data in cloud storage
12. Command and Control: communicating with compromised systems to control them, i.e., mimicking normal web traffic to communicate with a victim network
13. Exfiltration: stealing data, i.e., transfer data to cloud account
14. Impact: manipulate, interrupt, or destroy systems and data, i.e., encrypting data with ransomware


## Use of MITRE ATT&CK Matrix:
- Adversary Emulation: Assesses security by applying intelligence about an adversary and how they operate to emulate a threat. ATT&CK can be used to create adversary emulation scenarios to test and verify defenses.
- Red Teaming: Acts as an adversary to demonstrate the impact of a breach. ATT&CK can be used to create red team plans and organize operations.
- Behavioral Analytics Development: Links together suspicious activity to monitor adversary activity. ATT&CK can be used to simplify and organize patterns of suspicious activity deemed malicious.
- Defensive Gap Assessment: Determines what parts of the enterprise lack defenses and/or visibility. ATT&CK can be used to assess existing tools, or test new tools prior to purchasing, to determine security coverage and prioritize investment.
- SOC Maturity Assessment: Similar to Defensive Gap Assessment, ATT&CK can be used to determine how effective a security operations center (SOC) is at detecting, analyzing, and responding to breaches.
- Implementing MITRE ATT&CK typically involves either manual mapping or integration with cybersecurity tools



###

## The Cyber Kill Chain: High Level Framework to understand the stages in a attack.

*7 stages* : 
1. Reconnaissance – Harvests email addresses, conference information, etc.
2. Weaponization – Couples exploit with backdoor into deliverable payload.
3. Delivery – Delivers weaponized bundle to the victim via email, web, USB, etc.
4. Exploitation – Exploits a vulnerability to execute code on a victim's system.
5. Installation – Installs malware on the asset.
6. Command & Control (C2) – Includes command channel for remote manipulation.
7. Actions on Objectives – Using 'Hands on Keyboards' access, intruders accomplish their original goals.
