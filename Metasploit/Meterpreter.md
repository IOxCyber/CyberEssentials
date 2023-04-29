### Meterpreter:
- a Metasploit attack payload that provides an interactive shell from which an attacker can explore the target machine and execute code.
- runs in memory and does not write itself to the disk on the target machine.
- Meterpreter also aims to avoid being detected by network-based IPS (Intrusion Prevention System) and IDS (Intrusion Detection System) solutions by using encrypted communication with the server
- `getpid` command, returns the process ID.
- Meterpreter will establish an encrypted (TLS) communication channel with the attacker's system.

### Meterpreter versions:
- Meterpreter versions could be to list out as below command.
- `msfvenom --list payloads | meterpreter` -  
- which version of Meterpreter to use?
-  - Target OS, Components available on the target system (Python, Java or PHP), Network connection types


### Meterpreter Commands: 
- `help` will list out all the available cmds.
- Meterpreter will provide you with three primary categories of tools:
- Built-in commands
- Meterpreter tools
- Meterpreter scripting
- 
