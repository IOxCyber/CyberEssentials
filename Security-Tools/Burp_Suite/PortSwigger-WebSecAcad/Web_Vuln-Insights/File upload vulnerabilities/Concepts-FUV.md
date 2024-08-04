## 1. File upload vulnerabilities:
- when a `web server allows users to upload files to its filesystem without validating their name, type, contents, or size.`
- If you're able to upload a web shell successfully, you effectively have `full control over the server.`, `read and write arbitrary files, exfiltrate sensitive data`, even use the server to pivot attacks against both internal infrastructure and other servers outside the network.

> Worst possible scenario is when a website allows you to upload server-side scripts, such as PHP, Java, or Python files, and is also configured to execute them as code.

### Content-Type response header:
- The `Content-Type` response header may provide clues as to what kind of file the server thinks it has served.
- If this header hasn't been explicitly set by the application code, it normally contains the result of the file extension/MIME type mapping.


