+++
title = 'Search Column in a Database'
date = 2023-12-12T11:11:22-06:00
category = ['sql']
draft = false
+++

Query 1
```sql
    SELECT OBJECT_NAME(object_id) 
    FROM sys.columns 
    WHERE name = 'COLUMN_NAME'

```


Query 2
```sql
    SELECT * 
    FROM INFORMATION_SCHEMA.COLUMNS 
    WHERE COLUMN_NAME LIKE '%COLUMN_NAME%' 
    
```