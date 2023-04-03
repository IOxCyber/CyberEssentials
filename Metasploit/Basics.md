## Metasploit Pro: GUI version
## Metasploit Framework: CLI version

## Usages:
- information gathering to post-exploitation.
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


  


















[^1]: a type of security software that uses signatures to identify malware. Signatures are bits of code that are unique to a specific piece of malware.
