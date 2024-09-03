## How to prevent OS command injection attacks
- `Never call out to OS commands from application-layer code.` use safer platform APIs.
- If you have to call out to OS commands with user-supplied input, then you must perform strong input validation.
- Some examples of effective validation include:
```
Validating against a whitelist of permitted values.
Validating that the input is a number.
Validating that the input contains only alphanumeric characters, no other syntax or whitespace.
Never attempt to sanitize input by escaping shell metacharacters. In practice, this is just too error-prone and vulnerable to being bypassed by a skilled attacker.
```
