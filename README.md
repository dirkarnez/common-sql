common-sql
==========
### Login
```sql
SELECT 
CustomerName
from 
(
SELECT 
COUNT(CustomerName) as B, 
* from 
  (SELECT 
  * 
  FROM Customers 
  WHERE CustomerName='Alfreds Futterkiste' 
  LIMIT 2
  )
) 
as A 
where A.B = 1;
```
