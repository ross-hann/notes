+++
title = 'Search Table and Views in a database'
date = 2023-12-12T11:11:22-06:00
category = ['sql']
draft = false
+++

Query 1
```sql
    SELECT  COLUMN_NAME AS 'ColumnName',
            TABLE_NAME AS  'TableName'
    FROM INFORMATION_SCHEMA.COLUMNS
    WHERE COLUMN_NAME LIKE '%MyName%'
    ORDER BY TableName, ColumnName;

```


Query 2
```sql
	SELECT t.name AS table_name,
	       SCHEMA_NAME(schema_id) AS schema_name,
	       c.name AS column_name
	FROM sys.tables AS t
	INNER JOIN sys.columns c ON t.OBJECT_ID = c.OBJECT_ID
	WHERE c.IKE '%MyColumn%'
    ORDER BY schema_name, table_name; 
    
```

