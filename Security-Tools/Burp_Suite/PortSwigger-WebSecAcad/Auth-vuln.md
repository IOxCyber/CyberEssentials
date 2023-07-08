## Authentication:
- the process of verifying the identity of a given user or client.
1. `Something you know`, such as a `password` or the answer to a security question. These are sometimes referred to as "knowledge factors".
2. `Something you have`, that is, a `physical device` like a mobile phone or security token. These are sometimes referred to as "possession factors".
3. `Something you are or do`, your `biometrics or patterns` of behavior. These are sometimes referred to as "inherence factors".

> Authentication is the process of verifying that a user really is who they claim to be, whereas authorization involves verifying whether a user is allowed to do something.

## Authentication Vulnerabilities:
1. The authentication mechanisms are weak if they fail to adequately protect against brute-force attacks.
2. Logic flaws or poor coding in the implementation allow the authentication mechanisms to be bypassed entirely by an attacker. This is sometimes referred to as "broken authentication".

## Brute-force attacks:
- a system of trial and error in an attempt to guess valid user credentials.
- `Pay Attention: Status codes, Error messages, Response times.`

## Labs:
1. Username enumeration via different responses: Use Brute Force > Check for the Http Status code (Odd/Unusual) > Perform Enumeration for username & then password.
2. 2FA Simple Bypass: After Login > Check the URL & Modify after login by Another User.
3. Password reset broken logic: The Token in the Password Reset link wasn't verified hence can be intercept & change the password for another user as well.
4. 


> Https Status Code: `Info 1xx`, `Success 2xx`, `Redirection 3xx`, `Client Error 4xx`, `Server Error 5xx`
