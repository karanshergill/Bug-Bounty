# Information Disclosure
Information disclosure, also known as information leakage, is when a website unintentionally reveals sensitive information to its users.

## Examples of Information Disclosure
  - Revealing the names of hidden directories, their structure, and their contents via a robots.txt file or directory listing
  - Providing access to source code files via temporary backups
  - Explicitly mentioning database table or column names in error messages
  - Unnecessarily exposing highly sensitive information, such as credit card details
  - Hard-coding API keys, IP addresses, database credentials, and so on in the source code
  - Hinting at the existence or absence of resources, usernames, and so on via subtle differences in application behavior

### Error Messages
Testing Parameters for Infmation Disclosure.

**Original Request**
```HTTP
GET /product?productId=1 HTTP/1.1
Host: 0a23001803408c45805f80c10041009a.web-security-academy.net
Cookie: session=9uTYTHDdqFqCe9H1u9mwziP4MnrUsE2n
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/114.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Referer: https://0a23001803408c45805f80c10041009a.web-security-academy.net/
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

**Modified Request**
```
```
