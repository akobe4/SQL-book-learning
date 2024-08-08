## Chapter 5: Querying Multiple Tables

**Cartesian Product**
```SQL 
mysql> SELECT c.first_name, c.last_name, a.address
    -> FROM customer c JOIN address a
    -> LIMIT 100;
```