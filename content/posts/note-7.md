+++
title = 'Date Queries'
date = 2023-12-12T11:11:22-06:00
category = ['sql']
draft = false
+++


```sql
    --Update date for 1 yr starting 2020-01-01
	UPDATE [TestDatabase].[dbo].[FirstTable]
	SET FirstDate = DATEADD(DAY, ABS(CHECKSUM(NEWID()) % 365), '2020-01-01')
	WHERE Col1 IS NULL

    --Update Year only, in this case changing the year to 2019
	UPDATE [TestDatabase].[dbo].[FirstTable]
	SET NewDate = DATEADD(year, 2019 - year(firstdate), firstdate) 

    --Add date to current date, in this case 360
	UPDATE [TestDatabase].[dbo].[FirstTable]
	SET NewDate = DATEADD(dd, 360, FirstDate) 

    --Return first two days of the Month
	SELECT * 
		,MONTH(DATE)
		,MONTH(DATEADD(M,-1,DATE))
		,CAST(CAST(YEAR(Date) AS VARCHAR(4)) + '-' +  CAST(MONTH(Date) AS VARCHAR(2)) + '-01' AS DateTime) AS ProcessMonth
		,DAY(DATE)
		,DAY(DATEADD(D,-2,DATE))
	FROM DBO.DateAdd
    WHERE MONTH(DATEADD(M,-1,DATE)) = MONTH(DATEADD(D,-2,DATE)) 
    
```