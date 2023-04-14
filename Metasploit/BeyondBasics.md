## The Metasploit DB:
- Need to start the PostgreSQL database, which Metasploit will use: **systemctl start postgresql**
- Initialize the Metasploit Database using: **msfdb init** (need to create non-rrot user to start the msfdb)
- check the database status using: **db_status**
- The database feature will allow you to create workspaces to isolate different projects: **workspace -help**
- once Metasploit is launched with a database, the help command, you will show the Database Backends Commands
- Nmap scan using the **db_nmap** will be saved to the database.
- We can check the result **hosts** & **services**
- If there is more than one host saved to the database, all IP addresses will be used when the **hosts -R** command is used.

## Use Cases: Metasploit allows you to quickly identify some critical vulnerabilities.

## Vulnerability Scanning:
- Use auxiliary/scanner/vnc/
> To use a module, search it with **Search** command

## Exploitation:
- Exploits are the most populated module category.
- **show payloads** (To check the payloads)
- Select a payload, **set payload_name**
- Set the required parameters
- **exploit or run**

> Backgrounding a session if working on more than one target simultaneously or on the same target with a different exploit and/or shell.
- **ctrl+z or ctrl+c**
- **sessions** command will list all active sessions.
- interact with any existing session using the **sessions -i** command followed by the session ID.

> meterpreter [Basic Cmds](https://www.offsec.com/metasploit-unleashed/meterpreter-basics/):
- **search** to search on remote host
**Note**: Use double slash after each folder to show the path to the file eg. cat c://xyz//folder1//folder2//file.txt
- **hashdump** to check the user & pwd
- 



