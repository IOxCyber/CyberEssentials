1. [Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)
- The dev didn't implement the controls to restrict the Admin Panel, anyone can access it.
- Append robots.txt in `academy.net/robots.txt`
- It will show the rules for web crawlers
- [image](https://github.com/user-attachments/assets/ab5ce686-303c-41f5-b685-726033779551)


## Robots.txt: `a way to control indexing and crawling by search engines`
- The robots.txt file is `not a security mechanism.`
- `publicly accessible`, can be viewed by navigating to http://example.com/robots.txt.
- Prevent search engines from indexing certain parts of their website.
- Manage server load by restricting access to resource-intensive pages.
- Keep certain site sections private or hidden from search engine results.

```
Example:

User-agent: *
Disallow: /private/
Disallow: /tmp/
Disallow: /test/

User-agent: Googlebot
Allow: /public/
Disallow: /not-for-google/
```
