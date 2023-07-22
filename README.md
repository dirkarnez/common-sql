common-sql
==========
### Login with tolerance to non-uinque user configuration
```sql
SELECT 
CustomerName
from 
(
  SELECT 
  COUNT(CustomerName) as B,
  CustomerName
  from 
    (
      SELECT 
      CustomerName
      FROM Customers 
      WHERE CustomerName='Alfreds Futterkiste' 
      LIMIT 2
    )
) as A
where A.B = 1;
```
