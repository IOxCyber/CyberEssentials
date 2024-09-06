# APIs (Application Programming Interfaces)
- `Enable software systems and applications to communicate and share data.`
- All dynamic websites are composed of APIs, so classic web vulnerabilities like SQL injection could be classed as API testing.


## API recon
- To start API testing, you first need to find out as much information about the API as possible, to discover its attack surface.
- To begin, you should identify API endpoints. These are locations where an API receives requests about a specific resource on its server. For example, consider the following GET request:
```HTML
GET /api/books HTTP/1.1
Host: example.com

Need to gather more info about API:
The input data the API processes, including both compulsory and optional parameters.
The types of requests the API accepts, including supported HTTP methods and media formats.
Rate limits and authentication mechanisms.
```

## API documentation:
- For Human: designed for developers to understand how to use the API. It may include detailed explanations, examples, and usage scenarios.
- For Machine: Processed by software for automating tasks like API integration and validation. It's written in structured formats like JSON or XML.

## Discovering API documentation:
- Even if API documentation isn't openly available, you may still be able to access it by browsing applications that use the API such as Burp Scanner to crawl the API or Manually thu browser.

## Note:
- You can use Burp Scanner to crawl and audit OpenAPI documentation, or any other documentation in JSON or YAML format. You can also parse OpenAPI documentation using the OpenAPI Parser BApp.
- You may also be able to use a specialized tool to test the documented endpoints, such as Postman or SoapUI

## Identifying API endpoints
- You can also gather a lot of information by browsing applications that use the API.
- While browsing the application, look for patterns that suggest API endpoints in the URL structure, such as `/api/.` Also look out for JavaScript files.
- Burp Scanner automatically extracts some endpoints during crawls, but for a more heavyweight extraction, use the JS Link Finder BApp.

## Interacting with API endpoints
- Once you've identified API endpoints, interact with them using Burp Repeater and Burp Intruder.

## Identifying supported HTTP methods
- The HTTP method specifies the action to be performed on a resource. For example:
```
GET - Retrieves data from a resource.
PATCH - Applies partial changes to a resource.
OPTIONS - Retrieves information on the types of request methods that can be used on a resource.

For example, the endpoint /api/tasks may support the following methods:

GET /api/tasks - Retrieves a list of tasks.
POST /api/tasks - Creates a new task.
DELETE /api/tasks/1 - Deletes a task
PUT 
```

## Identifying supported content types
- API endpoints often expect data in a specific format. They may therefore behave differently depending on the content type of the data provided in a request. Changing the content type may enable you to:
```
Trigger errors that disclose useful information.
Bypass flawed defenses.
Take advantage of differences in processing logic. 
For example, an API may be secure when handling JSON data but susceptible to injection attacks when dealing with XML.
```