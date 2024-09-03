# OS command injection: AKA `Shell injection`:
- Allows an attacker to execute operating system (OS) commands on the application server running, and typically fully compromise the application and its data.
- An attacker can leverage an OS command injection vulnerability to compromise other parts of the hosting infrastructure, and exploit trust relationships to pivot the attack to other systems within the organization.

# Injecting OS commands:
- Eg. a shopping application lets the user view whether an item is in stock in a particular store:
- URL: `https://insecure-website.com/stockStatus?productID=381&storeID=29`
- Backend CMD Execution: `stockreport.pl 381 29`
- Injection: `& echo aiwefwlguh &`
- After Injection: `stockreport.pl & echo aiwefwlguh & 29`
```xml
Error - productID was not provided
aiwefwlguh
29: command not found
The three lines of output demonstrate that:

Explanation:
The original stockreport.pl command was executed without its expected arguments, and so returned an error message.
The injected echo command was executed, and the supplied string was echoed in the output.
The original argument 29 was executed as a command, which caused an error.
```

## Useful CMD:
```PowerShell
Purpose of command	Linux	Windows
Name of current user	whoami	whoami
Operating system	uname -a	ver
Network configuration	ifconfig	ipconfig /all
Network connections	netstat -an	netstat -an
Running processes	ps -ef	tasklist
```



