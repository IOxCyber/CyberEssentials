## The Metasploit DB:
- Need to start the PostgreSQL database, which Metasploit will use: `systemctl start postgresql`
- Initialize the Metasploit Database using: `msfdb init` (need to create non-rrot user to start the msfdb)
- check the database status using: `db_status`
- The database feature will allow you to create workspaces to isolate different projects: `workspace -help`
- once Metasploit is launched with a database, the help command, you will show the Database Backends Commands
- Nmap scan using the `db_nmap` will be saved to the database.
- We can check the result `hosts` & `services`
- If there is more than one host saved to the database, all IP addresses will be used when the `hosts -R` command is used.

> Use Cases: Metasploit allows you to quickly identify some critical vulnerabilities.

---
---

# Available Modules:
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/6e0ea17a-95e2-42b2-9f24-81376e9f6cde)

## 1. Exploit Modules:
- To `take advantage of vulnerabilities in software, allowing for control over the target system.`
- To gain unauthorized access to a system by exploiting a known/discovered vulnerability.

## 2. Auxiliary Modules:
- To assist in `tasks such as scanning, fuzzing, and data gathering without exploiting a target.`
- Running a port scan on a network to identify open services using an auxiliary module.

## 3. Post-Exploitation Modules:
- To perform actions on a compromised system such as `maintaining access, gathering additional information, and pivoting to other systems.`
- Using a post-exploitation module to extract passwords from memory on a compromised machine.

## 4. Payloads:
- To perform specific actions upon successful exploitation, such as creating a remote shell or executing commands.
- Deploying a reverse shell payload to maintain remote access to a compromised system.

## 5. Encoders:
- To transform payloads into encoded formats to evade detection mechanisms.
- Encoding a payload to bypass antivirus detection before deploying it on a target system.

## 6. NOPs (No-Operation Instructions):
- To pad the exploit code, ensuring proper alignment and execution of the payload.
- Inserting NOPs into the shellcode `to prevent crashing the target` application due to misalignment.

## 7. Evasion Modules:
- To modify payloads and techniques `to bypass security measures` such as antivirus and intrusion detection systems.
- Using an evasion module `to MASK/Conceal a payload from antivirus software,` increasing the likelihood of successful exploitation.

---
---

# Order of Using Metasploit Modules in a Penetration Test:
## 1. Reconnaissance Phase:
### Auxiliary Modules:
- Purpose: `Gather information about the target.`
- Example: Use auxiliary/scanner/portscan/tcp to scan for open ports and auxiliary/scanner/http/title to identify web services.

## 2. Weaponization Phase:
### Payloads:
- Purpose: Create payloads that will be used in the exploitation phase.
- Example: Use msfvenom to generate a payload like a reverse shell.

## 3. Delivery Phase:
### Exploit Modules:
- Purpose: Deliver the exploit to the target to take advantage of a vulnerability.
- Example: Use exploit/windows/smb/ms17_010_eternalblue to exploit a vulnerability in SMB.

## 4. Exploitation Phase:
### Payloads:
- Purpose: Execute the payload on the target system upon successful exploitation.
- Example: Deploy a reverse_tcp payload to gain a remote shell.

## 5. Installation Phase:
### Post-Exploitation Modules:
- Purpose: Maintain access and perform further actions on the compromised system.
- Example: Use post/windows/manage/persistence to create a persistent backdoor.

## 6. Command and Control (C2) Phase:
### Encoders:
- Purpose: Encode payloads to evade detection during execution.
- Example: Use msfvenom with an encoder like x86/shikata_ga_nai to evade antivirus.

## 7. Actions on Objectives Phase:
### Post-Exploitation Modules:
- Purpose: Gather sensitive data and perform other actions based on the test objectives.
- Example: Use post/windows/gather/hashdump to retrieve password hashes.

> Exploits are the most populated module category.

## To Search in Modules:
- To search the Modules/Decription: `search <keyword> <option>`
- TIPS & Tricks: `help search`
- To List out all Exploits Modules: `search type:exploit`
- To List out all Evasions Modules: `search type:evasion` etc
- eg. search eternal (will list out all the modules with eternal blue exploit in its name/description.

## Backgrounding a Session
- if working on more than one target simultaneously or on the same target with a different exploit and/or shell.
- To list all active sessions: `sessions`
- To interact with any existing session using: `sessions -i session_ID`
- To exit from the session: `ctrl+z or ctrl+c`

## meterpreter
- [Basic Cmds](https://www.offsec.com/metasploit-unleashed/meterpreter-basics/):
- `search` to search on remote host
- Use `double slash` after each folder to show the path to the file eg. cat `c://xyz//folder1//folder2//file.txt`
- `hashdump` to check the user & pwd
