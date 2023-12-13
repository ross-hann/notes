+++
title = 'Get Metadata for the tables'
date = 2023-12-12T11:11:22-06:00
category = ['sql']
draft = false
+++


```sql
    --If new table does not exist and you want to make a copy of old table with everything
		SELECT * INTO NewTable FROM OldTable
	Else
		INSERT INTO destinationTable
        SELECT * FROM sourceTable
	
    --Copy only Top 20 records 
		INSERT INTO NewTable SELECT TOP 20 * FROM OldTable

	--Create the same table but with no data
        SELECT * INTO Table1 FROM Table1Copy WHERE 1 = 2
    
```