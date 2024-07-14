# Payload Types in Intruder Module:

1. Simple list:
```
Definition: Basic list of payloads used for testing input fields.
Example: Testing a login form with common passwords like "password123".
```

2. Runtime file:
```
Definition: Loads payloads from a file during runtime for varied inputs.
Example: Injecting SQL injection payloads from a text file into a search bar.
```

3. Recursive grep:
```
Definition: Recursively searches for payloads within directories and subdirectories.
Example: Searching for XSS payloads in all JavaScript files within a web application.
```

4. Custom Iterator:
```
Definition: Customizes payloads using iterators for iterative testing.
Example: Iteratively testing username fields with a combination of names and numbers.
```

5. Character substitution:
```
Definition: Replaces characters in payloads to evade input filters.
Example: Using variations like "l33t" speak (e.g., "p@ssw0rd") to bypass password filters.
```

6. Case modification:
```
Definition: Alters letter case in payloads to bypass case-sensitive filters.
Example: Testing for vulnerabilities by varying the capitalization of SQL keywords.
```

7. Illegal Unicode:
```
Definition: Inserts illegal or anomalous Unicode characters in payloads.
Example: Injecting malformed UTF-8 characters to bypass input validation in form fields.
```

8. Character black:
```
Definition: Tests for blacklist filtering by injecting restricted characters.
Example: Attempting to bypass a filter that blocks special characters in a comment form.
```

9. Numbers:
```
Definition: Generates numerical payloads for testing numeric inputs.
Example: Injecting sequential numbers into a price field to test for integer overflows.
```

10. Date:
```
Definition: Tests date formats and boundaries as payloads.
Example: Checking for SQL injection vulnerabilities by injecting date values in a search form.
```

11. Brute forcer:
```
Definition: Iteratively tests all possible combinations for brute force attacks.
Example: Attempting to guess a weak password by systematically trying every possible combination of characters.
```

12. Null payloads:
```
Definition: Injects null characters as payloads to test application behavior.
Example: Testing a file upload function by injecting null bytes to bypass file type restrictions.
```

13. Character robber:
```
Definition: Removes characters from payloads to evade input validation.
Example: Testing a username field by stripping out special characters to bypass restrictions.
```

14. Bit flipper:
```
Definition: Alters individual bits in payloads to test for input filtering weaknesses.
Example: Attempting to bypass checksum validation in a cryptographic application by flipping bits.
```

15. Username generator:
```
Definition: Generates usernames as payloads for authentication testing.
Example: Testing a login form with a variety of usernames to identify weak authentication mechanisms.
```

16. ECB block shuffler:
```
Definition: Manipulates payloads to test cryptographic weaknesses in ECB block ciphers.
Example: Injecting manipulated blocks of plaintext to detect patterns in ECB mode encryption.
```

17. Extension generator:
```
Definition: Appends file extensions to payloads for testing file upload functionalities.
Example: Uploading a malicious file with extensions like ".exe" or ".php" to exploit file upload vulnerabilities.
```

18.Copy other payloads:
```
Definition: Duplicates existing payloads for varied testing scenarios.
Example: Using known XSS payloads to craft new variations for testing different input fields.
```


# Code Examples:
```
Simple list: ["admin", "test", "guest"]
Runtime file: Read payloads from `payloads.txt`
Recursive grep: Grep for `<input` elements to find new injection points
Custom Iterator: ["a1", "a2", "b1"]
Character substitution: "password" -> "p@ssword"
Case modification: "admin" -> "ADMIN"
Illegal Unicode: "\uD800"
Character blacklist: Generate payloads without "a" or "1": "p@ssw0rd"
Numbers: 1, 2, 3, ...
Date: "2024-07-14"
Brute forcer: "aa", "ab", ...
Null payloads: ""
Character robber: Remove "a" from "password": "pssword"
Bit flipper: "A" (0x41) -> "B" (0x42)
Username generator: "admin", "user1"
ECB block shuffler: Shuffling 16-byte blocks
Extension generator: "file.php", "file.html"
Copy other payloads: Duplicate payloads from a simple list
```
