1. `Check the file extension against a whitelist of permitted extensions` rather than a blacklist of prohibited ones. It's much easier to guess which extensions you might want to allow than it is to guess which ones an attacker might try to upload.
2. Make sure the `filename doesn't contain any substrings` that may be interpreted as a directory or a traversal sequence (../).
3. `Rename uploaded files to avoid collisions` that may cause existing files to be overwritten.
4. `Do not upload files to the server's permanent filesystem` until they have been fully validated.
5. As much as possible, `use an established framework` for preprocessing file uploads rather than attempting to write your own validation mechanisms.
