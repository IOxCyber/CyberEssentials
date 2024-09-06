[HTTP-Methods AKA HTTP-Verb](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
- An HTTP method is 'SAFE' if it doesn't alter the state of the server. In other words, 'a method is safe if it leads to a read-only operation.' eg. GET, HEAD, or OPTIONS.
- An HTTP method is 'idempotent' if the intended effect on the server of making a single request is the same as the effect of making several identical requests. eg. common non-idempotent methods: POST, PATCH, CONNECT
> All safe methods are idempotent, as well as PUT and DELETE
- 'cacheable' response is an HTTP response that can be cached, that is stored to be retrieved and used later, saving a new request to the server. eg. common cacheable methods: GET, HEAD
