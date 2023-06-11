common-sql
==========
### Login
```sql
SELECT *
FROM my_table
WHERE my_column = 'my_value'
AND (SELECT COUNT(*)
     FROM my_table
     WHERE my_column = 'my_value') <= 1;
```
