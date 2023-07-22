common-sql
==========
### Login with tolerance to non-uinque user configuration
```sql
# Replace City to user name, Customers to user table
SELECT 
City
from 
(
  SELECT 
  City
  from 
    (
      SELECT 
      City
      FROM Customers 
      WHERE City='London'
      LIMIT 2
    )
  GROUP BY City
  HAVING COUNT(City) = 1
)
```
