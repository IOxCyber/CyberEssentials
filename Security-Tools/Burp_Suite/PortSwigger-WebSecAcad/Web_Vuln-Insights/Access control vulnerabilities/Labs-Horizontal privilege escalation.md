# Horizontal privilege escalation 
- `occurs if a user is able to gain access to resources belonging to another user, instead of their own resources.`

## Lab 1: [User ID controlled by request parameter](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter)
- Login with given Creds > Modify Parameter `my-account?id=carlos` > Obtain the API Key > Submit it.


## Lab 2: [User ID controlled by request parameter, with unpredictable user IDs](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-unpredictable-user-ids)
- Login with given Creds > Find a Post from Asked User > Find their GUID > Modify Parameter `my-account?id=5752d0a8-b2b0-459f-8fb6-2f2ac42cb337` > Obtain the API Key > Submit it.

## Lab 3: [User ID controlled by request parameter with data leakage in redirect](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-data-leakage-in-redirect)
- Login with given Creds > Modify Parameter `my-account?id=carlos` > Observe the Redirect Request > Obtain the API Key > Submit it.
- Use `http-history` tab in BurpSuite to check the response.

# Horizontal to vertical privilege escalation:
## Lab 4: [User ID controlled by request parameter with password disclosure](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-password-disclosure)
- Login with given Creds > Modify Parameter `my-account?id=administrator` > Intersept the Request > Observe the Response in Repeater > Get the Password > Login to Admin Penal > Del User
- ![image](https://github.com/user-attachments/assets/87854ee8-55fa-49fb-8e0a-15f3c4251ff9)

