## Intruder: (BruteForcing) ctrl+i
- `Burp Suite's in-built fuzzing tool/Module.`
- It allows us to take a request (usually captured in the Proxy before being passed into Intruder) and use it as a template to send many more requests with slightly altered values automatically.
- Very similar to that provided by command-line tools such as Wfuzz or Ffuf.
- Intruder is used to automate a large number of requests with parameterized values/ Bruteforcing.
- `Can use multiple payload positions in any of the Intruder attack types in Burp Suite.`

## `Repeater is used for manually tampering and replaying requests, and Intruder is used to automate a large number of requests with parameterized values.`

## There are four other Intruder sub-tabs:
1. Positions: To select an Attack Type (Single: Sniper, Battering Ram, Multiple: PitchFork, Cluster Bomb).
2. Payloads: To select values to insert into each of the positions. (e.g. add a prefix or suffix, match and replace, or skip if the payload matches a defined regex).
3. Resource Pool is not particularly useful to us in Burp Community. It allows us to divide our resources between tasks.
4. Options: 

> Fuzzing is when we take a set of data and apply it to a parameter to test functionality or to see if something exists.

## Notes:
- When we are looking to perform an attack with Intruder, the first thing we need to do is look at positions.
- Burp will attempt to determine the most likely places we may wish to insert a payload automatically, `highlighted in $green$`

## Attack Type:
1. Sniper: `Single Payload Set`
- This attack uses a single set of payloads. It places each payload into each defined position one at a time.
- Useful for `testing single input fields, like a username or password field.`
- Request: `uid=$username$&passw=admin&btnSubmit=Login`
- Payload Position: $username$
- Payloads: admin, user1, test
![image](https://github.com/user-attachments/assets/2e647e5e-feaa-4333-831d-8b631b273f70)
```
Requests: 3
uid=admin&passw=password&btnSubmit=Login
uid=user1&passw=password&btnSubmit=Login
uid=test&passw=password&btnSubmit=Login
```
> Note: If we use more than 1 payload position in a request, the payload will be first substituted to first position than other positions, one at a time.
- eg. Requests Count = Payload Positions X Payloads List
![image](https://github.com/user-attachments/assets/ef3e0c7f-7e8b-46b0-9051-8d87ee7dd35f)


2. Battering Ram: `To check if user is using same string as username & password`
- Takes one set of payloads (e.g. one wordlist). Unlike Sniper, the Battering ram puts the `same payload in every Payload $position$`
- Request: `uid=$username$&passw=$password$&btnSubmit=Login`
![image](https://github.com/user-attachments/assets/cd616557-5548-46d8-ba28-b8f6f1d1e2ec)

```
Payload Position: $username$, $password$
Payloads: admin, user1, test

Requests: 3
uid=admin&passw=admin&btnSubmit=Login
uid=user1&passw=user&btnSubmit=Login
uid=test&passw=guest&btnSubmit=Login
```

3. PitchFork: `Puts the payloads in Pairs from both sets of Payloads`
- Uses one payload set per position (up to a maximum of 20) and iterates through them all at once, needs two worklists (One for position1, Second for position2)
- Set1 Payloads:
![image](https://github.com/user-attachments/assets/346745cb-1e02-477c-b128-0a9392351d5b)

- Set2 Payloads:
![image](https://github.com/user-attachments/assets/c6433eaa-2927-4f76-a0e4-d990a9643ab8)

- Result:
![image](https://github.com/user-attachments/assets/991c3a54-4afe-43ef-b229-6565138ab1d6)

```
Payload Sets:
Set 1 (uid field): admin, user, guest
Set 2 (passw field): adminPass, userPass, guestPass

Requests: 3
uid=admin&passw=adminPass&btnSubmit=Login
uid=user&passw=userPass&btnSubmit=Login
uid=guest&passw=guestPass&btnSubmit=Login
```


4. ClusterBomb: `Multiple payload sets, testing all permutations of payload combinations`
- Allows us to choose multiple payload sets: one per position, up to a maximum of 20.
- Make sure that every possible combination of payloads is tested.
- It tries every combination of values, equal to the number of lines in each payload set multiplied together
- `Request = multiplication of lines in payloads`
- Set1
![image](https://github.com/user-attachments/assets/aca70423-edd0-400d-9e3a-f28d29ce9e15)

- Set2
![image](https://github.com/user-attachments/assets/37f49b35-b5fd-4c4e-9126-a266414b2d31)

- Result:
![image](https://github.com/user-attachments/assets/78871431-c3c5-48c3-9678-2f4b87025209)

```eg. 
Set 1 (uid field): admin, user
Set 2 (passw field): adminPass, userPass

Requests: 4
uid=admin&passw=adminPass&btnSubmit=Login
uid=admin&passw=userPass&btnSubmit=Login
uid=user&passw=adminPass&btnSubmit=Login
uid=user&passw=userPass&btnSubmit=Login
```

## Payloads:
1. Payload Sets: Allows us to choose which position we want to configure a set for as well as what type of payload we would like to use.
- Note: Multiple positions should be read from top to bottom, then left to right when being assigned numbers in the "Payload set" dropdown.
2. Payload Options: Let you make a list of string to use as payloads.
3. Payload Processing: Allows us to define rules to be applied to each payload in the set before being sent to the target.
4. Payload Encoding: allows us to override the default URL encoding options that are applied automatically to allow for the safe transmission of our payload.

## Tips:
- Sort out by Length after Attack: Request with the shorter response length was made with the valid credentials.
- Ensure there must be **2 blank lines** in request before sending it for repeater.

## Macros:
- Define a Macro:
1. "Project Options" > "Sessions" sub-tab.
2. Scroll down to the bottom of the sub-tab to the "Macros" section and click the "Add" button.
3. The menu that appears will show us our request history. If there isn't a GET request to http:/requiredPage in the list already, navigate to that location in your browser and you should see a suitable request appear in the list.
4. With the request selected, click Ok.
5. Finally, give the macro a suitable name, then click "Ok" again to finish the process.

- Set Session Handling rules:
1. Still in the "Sessions" sub-tab of Project Options, scroll up to the "Session Handling Rules" section and choose to "Add" a new rule.
2. A new window will pop up with two tabs in it: "Details" and "Scope". We are in the Details tab by default.
3. Fill in an appropriate description, then switch over to the Scope tab.
4. In the "Tools Scope" section, deselect every checkbox other than Intruder -- we do not need this rule to apply anywhere else.
5. In the "URL Scope" section, choose "Use suite scope"; this will set the macro to only operate on sites that have been added to the global scope (as was discussed in Burp Basics). If you have not set a global scope, keep the "Use custom scope" option as default and add http://MACHINE_IP/ to the scope in this section.
6. Click the "Add" button -- this will cause a dropdown menu to appear with a list of actions we can add.
7. Select "Run a Macro" from this list.
8. Select "Update only the following parameters", then click the "Edit" button next to the input box below the radio button.
9. In the "Enter a new item" text field, type "loginToken". Press "Add", then "Close".
10. Select "Update only the following cookies", then click the relevant "Edit" button.
11. Enter "session" in the "Enter a new item" text field, press "Add", then "Close".
12. Finally, press "Ok" to confirm our action.





