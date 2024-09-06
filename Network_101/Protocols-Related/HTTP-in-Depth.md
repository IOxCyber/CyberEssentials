## [Hypertext Transfer Protocol (HTTP):](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
- An application-layer protocol
- Stateless protocol, meaning that the server does not keep any data (state) between two requests.
- `Hypertext` to enable web browsers to retrieve and display web pages, images, videos, and other resources from web servers. eg. Hyperlinks, Non-linear Navigation[^1], Interconnected Information.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberEssentials/assets/40174034/62b1c914-3c69-4452-8c74-4e516157d458">

## HTTP Messages:
- There are two types of HTTP messages ie. `Requests and responses`.

## HTTP Request: Client requests to Server for WebPages.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberEssentials/assets/40174034/e5a6a682-20f3-4b17-9db8-cc3187b0303a">
> Example:
```
GET /example-page HTTP/1.1
Host: developer.mozila.org
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/96.0.4664.45 Safari/537.36
Accept: text/html,application/xhtml+xml
```
### Requests consist of the following elements:
- `Method: Specifies the HTTP method being used`. eg. "GET" method. The GET method is used to retrieve data from the server, specifically, to request a specific resource identified by the URL.
- `URI (Uniform Resource Identifier): represents the path to the resource` being requested. In this case, it is `/example-page` & the URI is relative to the host (www.example.com).
- `HTTP Version: the HTTP version being used` is specified. Here, it is "HTTP/1.1." HTTP/1.1 is a widely used version of the HTTP protocol
- `Host: specifies the domain name` of the server to which the request is being sent. eg. developer.mozila.org
- `User-Agent: This header provides information about the client making the request.`
- `Accept: indicates the media types (content types) that the client can understand or accept as a response.`

## HTTP Response: Server responses to Client with Webpage.
- <img width="500" alt="image" src="https://github.com/IOxCyber/CyberEssentials/assets/40174034/5ff597fb-4547-465c-be12-c61de980a484">

> Example:
```
HTTP/1.1 200 OK
Date: Wed, 21 Jul 2023 12:00:00 GMT
Server: Apache/2.4.41 (Unix)
Content-Length: 182
Content-Type: text/html; charset=UTF-8

<!DOCTYPE html>
<html>
<head>
    <title>Welcome to Example Website</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>Welcome to our example website.</p>
</body>
</html>

```
### Responses consist of the following elements:
- `Status Line: includes the HTTP version, status code, and status message`. Here, the `status line is HTTP/1.1 200 OK`. It means HTTP version is 1.1, the status code is 200 (OK), and the status message is "OK".
- `Headers: provide additional information about the response.` eg.
  - `Date: The date and time of response` was generated.
  - `Server: The type and version of the server software` used (Apache/2.4.41 in this case).
  - `Content-Length: The size of the response` body in bytes (182 bytes in this example).
  - `Content-Type: The MIME type of the response body` (text/html; charset=UTF-8), indicating that the response contains HTML content encoded with UTF-8.
- `Blank Line: separates the headers from the response body.`
- `Response Body: contains the actual content sent back by the server`. In this example, it is an HTML document.

## HTTP response status code: [More](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- <img width="500" alt="image" src="https://github.com/cybersome/Linux-octo/assets/40174034/2df5fede-4375-4e17-8dd3-dc660e39e6de">









[^1]: Imagine reading a book, where you start at the first page and read through it page by page until you reach the end. That's a linear way of reading. Now, think of a web page with clickable links. When you click on a link, it takes you to another web page or a different section of the same page. You can then click on other links and move around the web in a non-linear fashion, not following a fixed order like in a book.
