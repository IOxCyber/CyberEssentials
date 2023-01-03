# The Basics:
- Written in Java, web app pen testing tool.
- useful in Web App & Mobile App assessment.
- Burp can capture and manipulate all of the traffic/packets between an attacker and a webserver
- to intercept, view, and modify web requests prior to them being sent to the target server.
- to intercept, view, and modify web requests prior to them being received by our browsers.
- 3 Editions 
  - Burp Suite Professionals: Automated Vulnerability Scanner, fuzzer/bruteforcer, generate reports & save projects, Built-in API to integrate with other tools, Extension support, access to collaborator.
  - Burp Suite Enterprise: To automate infra vul scanning just like Nessus.
  - Burp Suite Community: Limited feature-set compare to Professional edition.

# Burp suite Community:
- Features:
  - Proxy: Allows us to intercept and modify requests/responses.
  - Repeater: Allows us to capture, modify, then resend the same request numerous times.
  - Intruder: Use to bruteforce or fuzz the endpoint.
  - Decoder: Use to decode captured info & encode a payload before sending it to target.
  - Comparer: Allows us to compare two pieces of data at either word or byte level.
  - Sequencer: For analyzing the quality of randomness of token eg. session cookie values or other random generated data.
 - Other features can be added by writing extensions in Java, [Jython[^1]](https://www.jython.org/), JRuby Interpreter or download from market place **BApp Store**.
 

[^1]:allows users to write programs in Python and compile them to Java bytecodes that run directly on a Java Virtual Machine, or JVM.
