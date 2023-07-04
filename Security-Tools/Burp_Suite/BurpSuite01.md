# The Basics:
- Written in Java, web app pen testing tool.
- Useful in Web & Mobile App Pen Testing.
- Burp can capture and manipulate all of the traffic/packets between an attacker and a webserver
- to intercept, view, and modify web requests prior to them being sent to the target server.
- to intercept, view, and modify web requests prior to them being received by our browsers.
- 3 Editions 
  - Burp Suite Professionals: Automated Vulnerability Scanner, fuzzer /brute forcer, generate reports & save projects, Built-in API to integrate with other tools, Extension support, access to collaborator.
  - Burp Suite Enterprise: To automate infra vul scanning just like Nessus.
  - Burp Suite Community: Limited feature set compared to the Professional edition.

# Burp suite Community:
- Features:
  - Proxy: Allows us to intercept and modify requests/responses.
  - Repeater: Allows us to capture, modify, then resend the same request numerous times.
  - Intruder: Use to bruteforce or fuzz the endpoint.
  - Decoder: Use to decode captured info & encode a payload before sending it to the target.
  - Comparer: Allows us to compare two pieces of data at either word or byte level.
  - Sequencer: For analyzing the quality of randomness of token eg. session cookie values or other randomly generated data.
 - Other features can be added by writing extensions in Java, [Jython[^1]](https://www.jython.org/), JRuby Interpreter, or downloading from marketplace **BApp Store**.

# Dashboard:
- Task: allows us to define background tasks.
- Event log: tells us what Burp Suite is doing
- Issue Activity: list out all of the vulnerabilities found by the automated scanner. (Pro & Professional Edition)
- Advisory section: gives more information about the vulnerabilities found, as well as references and suggested remediations.

# Navigation:
- done entirely using the top menu bars.
- By Windows Option: view the Menu Bar separately in new window.

# Shortcut:
- CTRL + Shft + (D for Dahsboard, T for Target, P for Proxy, I for Intruder, R for Repeater)

# Option:
1. Global settings:
  - Apply everytime we open Brup Suite, can be found in the User options tab along the top menu bar.
  - Connections sub-tab allow us to control how Burp makes connections to targets.
  - TLS sub-tab allows us to enable and disable various TLS (Transport Layer Security) options such as Certificate.
  - Display allows us to change how Burp Suite looks.
  - Misc sub-tab contains a wide variety of settings, including the keybinding table (HotKeys i.e Set a shortcut).
  

2. Project-specific:
  - Apply to current Project, settings can be found in the Project options tab.
  - Connections: to set a proxy for just the project, overriding any proxy settings that you set in the User options tab.
  - HTTP: defines how Burp handles various aspects of the HTTP protocol.
  - TLS allows us to override application-wide TLS options
  - Sessions: provides us with options for handling sessions, allows us to define how Burp obtains, saves, and uses session cookies that it receives from target sites.
  -  Misc sub-tab than in the equivalent tab for the "User options" section.
 
 
 





 
 

[^1]:allows users to write programs in Python and compile them to Java bytecodes that run directly on a Java Virtual Machine, or JVM.
