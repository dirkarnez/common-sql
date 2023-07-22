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
    FROM Customers 
    WHERE City='London'
    LIMIT 2
  )
GROUP BY City
HAVING COUNT(City) = 1
```
```go
db.Table("Customers").
    Select("City").
    Where("City = ?", "London").
    Limit(2).
    Group("City").
    Having("COUNT(City) = 1").
    Pluck("City", &result)
```
