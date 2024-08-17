# Lab 1: File path traversal, simple case [i](https://portswigger.net/web-security/file-path-traversal/lab-simple)
- Capture image request > Send to Repeater > Modify the filename parameter, giving it the value: `../../../etc/passwd`
- ![image](https://github.com/user-attachments/assets/209ca98e-73f7-4b31-bac8-776406732055)

> Make sure the Proxy is set for http/https in Browser.

# Lab 2: File path traversal, traversal sequences blocked with absolute path bypass [i](https://portswigger.net/web-security/file-path-traversal/lab-absolute-path-bypass)
- Capture image request > Send to Repeater > Modify the filename parameter, giving it the value: `/etc/passwd`
- ![image](https://github.com/user-attachments/assets/53cf1107-9614-498f-951b-7cbc7d3dfcca)

# Lab 3: File path traversal, traversal sequences stripped non-recursively [i](https://portswigger.net/web-security/file-path-traversal/lab-sequences-stripped-non-recursively)
- Capture image request > Send to Repeater > Modify the filename parameter, giving it the value: `....//....//....//etc/passwd`
- ![image](https://github.com/user-attachments/assets/0f29d85d-e937-48f6-a98d-a44608f5f55c)

# Lab 4: File path traversal, traversal sequences stripped with superfluous URL-decode [i](https://portswigger.net/web-security/file-path-traversal/lab-superfluous-url-decode)
- Capture image request > Send to Intruder > Modify the filename parameter i.e $$ > Use `fuzzing - Path Traversal`, Sniper > Start > Filter on 200 > Send the request to Repeater > Observe the response
- ![image](https://github.com/user-attachments/assets/1a90634e-7dd9-4d3a-a2aa-c5d4649ad278)

# Lab 5: 

