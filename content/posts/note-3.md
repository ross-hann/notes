+++
title = 'Add a new column and update it with random numbers'
date = 2023-12-12T11:11:22-06:00
category = ['sql']
draft = false
+++


```sql
	ALTER TABLE [TestDatabase].[dbo].[AnalysisReport]
	ADD COL_ID INT
	
	--For 4 digits ranging from 1000 - 4000 mod by 1000 and add 4000
	UPDATE [TestDatabase].[dbo].[AnalysisReport]
	SET COL_ID = ABS(CHECKSUM(NEWID()))%1000 + 1000
	
	--For Alphanumeric values, 8 characters
	UPDATE [TestDatabase].[dbo].[AnalysisReport]
	SET COL_ID = LEFT(NEWID(), 8)
	
	--For Alphanumeric values, 10 characters
	UPDATE [TestDatabase].[dbo].[AnalysisReport]
	SET COL_ID = LEFT(REPLACE(NEWID(), '-', ''), 10)

    
```