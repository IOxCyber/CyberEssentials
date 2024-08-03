# IDOR: Insecure Direct Object Reference
- Arises when an application uses user-supplied input to access resources or functions directly.
- `Most commonly associated with horizontal privilege escalation`, but can also arise with vertical privilege escalation.

## Type: 
### 1. IDOR vulnerability with direct reference to database objects.
- Modifying the customer_number to gather other user profiles/accounts.
- eg. https://insecure-website.com/customer_account?`customer_number=132355`

### 2. IDOR vulnerability with direct reference to static files.
- a website might save chat message transcripts to disk using an incrementing filename.
- Modifying the static file name/number & observing the response.
- eg. https://insecure-website.com/static/`12144.txt`

## Lab [Insecure direct object references](https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references)
- A live chat file is getting downloaded from a saved location from the server when we click on Transcripts > Capture a request of `View Transcripts` > Modify the Parameter, change file name > Send it  > Observe the response
- ![image](https://github.com/user-attachments/assets/2dc6db93-7bd4-49e6-8a5c-0473c1aa43e4)

> If an attacker changes id=123 to id=124 and can access another user's profile without authorization, it's an IDOR vulnerability.
