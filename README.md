common-sql
==========
### Login with tolerance to non-uinque user configuration
```sql
# Replace City to user name
SELECT 
City,
B
from 
(
  SELECT 
  COUNT(City) as B,
  City
  from 
    (
      SELECT 
      City
      FROM Customers 
      WHERE City='London' 
    ) GROUP BY City
) as A
where A.B = 1;
```
