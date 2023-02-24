## Decoder, Comparer and Sequencer tools:

1. Decoder:
- Enables you to transform plain text data into encrypted data using common encoding and decoding formats.
- Encoding (Plain text to Encrypted Text) & Decoding (Encrypted Text to Plain Text)
- Decoding/Encoding Methods:
   - Plain: Plaintext is what we have before performing any transformations.
   - URL: URL encoding is used to make data safe to transfer in the URL of a web request, involves exchanging characters for their ASCII character code in hexadecimal format, preceded by a percentage symbol (%), [ASCII](https://www.asciitable.com/)
   - HTML: Encoding text as HTML Entities involves replacing special characters with an ampersand (&) followed by either a hexadecimal number or a reference to the character being escaped, then a semicolon (;). For example, a quotation mark has its own reference: &quot;. When this is inserted into a webpage, it will be replaced by a double quotation mark ("). This method prevents **XSS** attacks.
  - Base64: Another widely used encoding method, base64 is used to encode any data in an ASCII-compatible format. It was designed to take binary data (e.g. images, media, programs) and encode it in a format that would be suitable to transfer over virtually any medium. (Binary Conversion)[https://madformath.com/calculators/basic-math/base-converters/decimal-to-binary-converter-with-steps/decimal-to-binary-converter-with-steps#calc100]
  - ASCII Hex: This option converts data between ASCII representation and hexadecimal representation. For example, the word "ASCII" can be converted into the hexadecimal number "4153434949". Each letter in the original data is taken individually and converted from numeric ASCII representation into hexadecimal. For example, the letter "A" in ASCII has a decimal character code of 65. In hexadecimal, this is 41.
  - Hex, Octal, and Binary: These encoding methods all **apply only to numeric inputs.**
  - Gzip: Gzip provides a way to compress data. It is widely used to reduce the size of files and pages before they are sent to your browser. 
 
 
2. Hashing in Decoder:
- Hashing is a one-way process that is used to transform data into a unique signature.
- A good hashing algorithm will ensure that every piece of data entered will have a completely unique hash.
- Hashes are frequently used to verify the integrity of files and documents
- Due to the one-way hashing process meaning that the hashes can never be reversed.
> eg. User > Created password > password hashed & stored > user try to login > app checks hashed password against password entered by USER > if matched then login > No, then incorrect password.

- Decoder allows us to generate hashsums for data directly within Burp Suite.

3. Comparer: 
- Comparer allows us to compare two pieces of data, either by ASCII words or by bytes.
- eg. Useful in comparing two response from the requests (Capture the requests > Modify it > Send the Response to Comparer to see the difference)







