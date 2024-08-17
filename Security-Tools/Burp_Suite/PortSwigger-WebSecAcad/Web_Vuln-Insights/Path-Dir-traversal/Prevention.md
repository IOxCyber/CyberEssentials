1. `Validate the user input before processing it`. Ideally, compare the user input with a whitelist of permitted values. If that isn't possible, verify that the input contains only permitted content, such as alphanumeric characters only.
2. `After validating the supplied input, append the input to the base directory` and use a platform filesystem API to canonicalize the path. Verify that the canonicalized path starts with the expected base directory.
 
