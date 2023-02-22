## Intruder: (BruteForcing) ctrl+i
- Intruder is Burp Suite's in-built fuzzing tool. It allows us to take a request (usually captured in the Proxy before being passed into Intruder) and use it as a template to send many more requests with slightly altered values automatically.
- very similar to that provided by command-line tools such as Wfuzz or Ffuf.
- Intruder is used to automate a large number of requests with parameterized values/ Bruteforcing.

> Repeater is used for manually tampering and replaying requests, and Intruder is used to automate a large number of requests with parameterized values.

## There are four other Intruder sub-tabs:
1. Positions allows us to select an Attack Type (Single: Sniper, Battering Ram, Multiple: PitchFork, Cluster Bomb).
2. Payloads allows us to select values to insert into each of the positions. (e.g. add a prefix or suffix, match and replace, or skip if the payload matches a defined regex).
3. Resource Pool is not particularly useful to us in Burp Community. It allows us to divide our resources between tasks.
4. Options: 

> Fuzzing is when we take a set of data and apply it to a parameter to test functionality or to see if something exists.

## Notes:
- When we are looking to perform an attack with Intruder, the first thing we need to do is look at positions.
- Burp will attempt to determine the most likely places we may wish to insert a payload automatically, highlighted in $green$

## Attack Type:
1. Sniper: **Single Payload Set**(a single file containing a wordlist or a range of numbers), take each payload from a payload set and put it into each defined position in turn. **requests = numberOfWords * numberOfPositions**
```eg. 2 words: admin, root & 2 positions
username=$admin$&password=$pwd$
username=$admin$&password=$pwd$
username=$user$&password=$root$
username=$user$&password=$root$
```
2. Battering ram: To check if user is using same string as username & password
- Takes one set of payloads (e.g. one wordlist). Unlike Sniper, the Battering ram puts the **same payload in every $position$**. 
```eg. 2 words: admin, pwd
username=$admin$&password=$admin$`
username=$pwd$&password=$pwd$
```
3. PitchFork: Just like having numerous Snipers running simultaneously but Pitchfork uses one payload set per position (up to a maximum of 20) and iterates through them all at once, needs two worklists (One for position1, Second for position2)
```eg. 
Usernames: admin,root
Passwords: pwd,passwd
username=$admin$&password=$pwd$`
username=$root$&password=$passwd$`
```
4. ClusterBomb: 
- Cluster bomb allows us to choose multiple payload sets: one per position, up to a maximum of 20.
- Pitchfork iterates through each payload set simultaneously but Cluster bomb iterates through each payload set individually, making sure that every possible combination of payloads is tested.
- It tries every combination of values, equal to the number of lines in each payload set multiplied together
- request = multiplication of lines in payloads
```eg. 
Usernames: admin,root
Passwords: pwd,passwd
username=$admin$&password=$pwd$`
username=$root$&password=$pwd$`
username=$admin$&password=$passwd$`
username=$root$&password=$passwd$`
```







