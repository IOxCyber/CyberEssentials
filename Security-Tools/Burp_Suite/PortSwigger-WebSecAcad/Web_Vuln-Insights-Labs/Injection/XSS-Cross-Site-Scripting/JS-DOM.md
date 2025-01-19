## Document Object Model (DOM):
- A programming interface provided by web browsers that `represents the structure of a webpage as a tree of objects.`
- Each object in the tree corresponds to a part of the document, such as elements, attributes, and text.

> a way for web browsers to represent a webpage so that JavaScript can interact with it.

```
HTML Document:

<!DOCTYPE html>
<html>
<head>
    <title>Example Page</title>
</head>
<body>
    <h1>Welcome to the DOM</h1>
    <p>This is a simple paragraph.</p>
    <div id="container">
        <ul>
            <li>Item 1</li>
            <li>Item 2</li>
            <li>Item 3</li>
        </ul>
    </div>
</body>
</html>
```


```
DOM Tree Representation:

Document
 └── html
      ├── head
      │    └── title
      │         └── "Example Page"
      └── body
           ├── h1
           │    └── "Welcome to the DOM"
           ├── p
           │    └── "This is a simple paragraph."
           └── div (id="container")
                └── ul
                     ├── li
                     │    └── "Item 1"
                     ├── li
                     │    └── "Item 2"
                     └── li
                          └── "Item 3"
```


## How DOM-Based XSS Can Harm a User
```
Cookie Theft: The attacker can steal cookies, including session cookies, which can lead to session hijacking.
Credential Theft: By manipulating the DOM, attackers can create fake login forms or intercept credentials entered by users.
Phishing: Attackers can change the appearance of the page to trick users into providing sensitive information.
Malicious Redirects: Attackers can redirect users to malicious sites.
Performing Actions on Behalf of the User: Attackers can perform actions such as changing account settings, making purchases, or sending messages on behalf of the user if the user is logged in.
```

