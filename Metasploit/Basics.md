## Metasploit Pro: GUI version
## Metasploit Framework: CLI version

<img width="379" alt="image" src="https://user-images.githubusercontent.com/40174034/232437770-add82a48-eb62-44dc-ab54-6c45cb9566ac.png">

## Usages:
- Can be used in any phase from `information gathering to post-exploitation`.
- a set of tools that allow information gathering, scanning, exploitation, exploit development, post-exploitation, and more.
- Components:
  - **msfconsole**: The main command-line interface.
  - Modules: small components built to perform a specific task, such as exploiting a vulnerability, scanning a target, or performing a brute-force attack.
  - Tools: Stand-alone tools that will help vulnerability research, vulnerability assessment, or penetration testing.

> Payloads are the code that will run on the target system.
> Exploit: A piece of code that uses a vulnerability present on the target system.
> Vulnerability: A design, coding, or logic flaw affecting the target system.

- Auxiliary: Any supporting module, such as scanners, crawlers and fuzzers can be found in this. eg. tree -L 1 auxiliary/
- Encoders: Allow you to encode the exploit and payload (a [^1]signature-based antivirus solution detects them) eg. tree -L 1 encoders/
- Evasion: Allow you to encode the exploit and payload, just like **Encoder** but with more sucess. eg tree -L 2 evasion/
- Exploits: tree -L 1 exploits/
- NOPs (No OPeration) do nothing, 
- Payloads are codes that will run on the target system. eg. tree -L 1 payloads/
  - Adapters: An adapter wraps single payloads to convert them into different formats
  - Singles: Self-contained payloads (add user, launch notepad.exe, etc.)
  - Stagers: Responsible for setting up a connection channel between Metasploit and the target system.
  - Staged payloads: first upload a stager on the target system then download the rest of the payload (stage)
  - Post modules: useful on the final stage of the penetration testing process eg. tree -L 1 post/

1. msfconsole: main interface to the Metasploit Framework
- will support most Linux commands
- **history**: to see commands you have typed
- **help**: can be used on its own or for a specific command
- Msfconsole is managed by context; this means that unless set as a global variable, all parameter settings will be lost if you change the module you have decided to use.
- **use**: To use the commands eg. use exploit/windows/smb/ms17_010_eternalblue command
- **show options**: To see the set context.
- **show**: can be used in any context followed by a module type (auxiliary, payload, exploit, etc.) to list available modules.
- **search**: will search the Metasploit Framework database for modules relevant to the given search parameter. eg. search SMB[^2]
- **info**: To get information on the modules.
- **set**: To set the parameters in msf prompt.
- **unset/unset all**: To clear any parameter/ parameters value.
- **setg**: (global set) Unlike set, It sets the value to all the modules.
- [Ranks of the Exploit](https://github.com/rapid7/metasploit-framework/wiki/Exploit-Ranking)
- exploit -z: command will run the exploit and background the session as soon as it opens
- background: command to background the session prompt and go back to the msfconsole prompt.
- sessions: command can be used from the msfconsole prompt or any context to see the existing sessions.


> Some modules support the check option. This will check if the target system is vulnerable without exploiting it.
> Note: A low-ranking exploit may work perfectly, and an excellent ranked exploit may not, or worse, crash the target system.
  
## Different prompts:
1. The regular command prompt eg. linux console
2. msf6 (The msfconsole prompt)
3. A context prompt eg. exploit(path2exploit)
4. The Meterpreter prompt (a Meterpreter agent was loaded to the target system and connected back to you)
5. A shell on the target system: This is a regular command line, and all commands typed here run on the target system.

## Often used Parameters:
1. RPORT: “Remote port”, the port on the target system the vulnerable application is running on.
2. RHOSTS: “Remote host”, the IP address of the target system. A single IP address or a network range can be set. This will support the CIDR (Classless Inter-Domain Routing) notation (/24, /16, etc.) or a network range (10.10.10.x – 10.10.10.y). You can also use a file where targets are listed, one target per line using file:/path/of/the/target_file.txt
3. PAYLOAD: The payload you will use with the exploit.
4. LHOST: “Localhost”, the attacking machine (your AttackBox or Kali Linux) IP address.
5. LPORT: “Local port”, the port you will use for the reverse shell to connect back to. This is a port on your attacking machine.
6. SESSION: Each connection established to the target system using Metasploit will have a session ID.



















[^1]: a type of security software that uses signatures to identify malware. Signatures are bits of code that are unique to a specific piece of malware.
[^2]: SMB (Server Message Block) is widely used in Windows networks for file sharing and even for sending files to printers. "EternalBlue" is an exploit allegedly developed by the U.S. National Security Agency (N.S.A.) for a vulnerability affecting the SMBv1 server on numerous Windows systems. then It was leaked by the cybercriminal group "Shadow Brokers". In May 2017, this vulnerability was exploited worldwide in the WannaCry ransomware attack.
