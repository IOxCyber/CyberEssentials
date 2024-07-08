# Meterpreter:
- a Metasploit attack payload that provides an interactive shell from which an attacker can explore the target machine and execute code.
- runs in memory and does not write itself to the disk on the target machine.
- Meterpreter also aims to avoid being detected by network-based IPS (Intrusion Prevention System) and IDS (Intrusion Detection System) solutions by using encrypted communication with the server
- `getpid` command, returns the process ID.
- Meterpreter will establish an encrypted (TLS) communication channel with the attacker's system.

## Meterpreter versions:
- Meterpreter versions could be to list out as below command.
- `msfvenom --list payloads | meterpreter` -  
- which version of Meterpreter to use?
-  - Target OS, Components available on the target system (Python, Java or PHP), Network connection types


## Meterpreter Commands: 
- `help` will list out all the available cmds.
- Meterpreter will provide you with three primary categories of tools:
- - Built-in commands
- - Meterpreter tools
- - Meterpreter scripting

## Migrate:
- To migrate to any process: `migrate pid`
- Migrating to another process will help Meterpreter interact with it.
- you can migrate to `Ongoing processes eg. word.exe, notepad.exe` and start capturing keystrokes sent by the user to this process.
> may lose user privileges if user migrates from a higher privileged (e.g. SYSTEM) user to a process started by a lower privileged user.

## Hashdump:
- `hashdump` command will list the content of the SAM database
- SAM (Security Account Manager) database stores user's passwords on Windows systems. These passwords are stored in the NTLM (New Technology LAN Manager) format.

## Search:
- `search` command is useful to locate files.

## Shell:
- The `shell` command will launch a regular command-line shell on the target system.

## Example:
- Check all the cmds available in meterpreter.
- Background the sessions & start using different modules if needed.

