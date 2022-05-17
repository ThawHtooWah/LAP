### MYSQL UPDATE and DELETE
> How to update/delete records from a table and how to delete(drop) a table
#### **Update a record from a table**
```sql
UPDATE table_name SET column_name = new_value WHERE condition;
```
```sql
mysql> UPDATE Girls SET Name = 'Alice' WHERE Name = 'Alica';
Query OK, 1 row affected (0.02 sec)
Rows matched: 1  Changed: 1  Warnings: 0

-- Before
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
|    2 | Betty | Betty2B |
+------+-------+---------+

-- After
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alice | Alice1A |
|    2 | Betty | Betty2B |
+------+-------+---------+
```

#### **Delete a record from a table**
```sql
DELETE FROM table_name WHERE condition;
```
```sql
mysql> DELETE FROM Girls WHERE Name = 'Alice';
Query OK, 1 row affected (0.01 sec)

-- Before
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alice | Alice1A |
|    2 | Betty | Betty2B |
+------+-------+---------+

-- After
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    2 | Betty | Betty2B |
+------+-------+---------+
```

#### **Delete (Drop) a table**
```sql
DROP TABLE table_name;
```
```sql
mysql> DROP TABLE Girls;
Query OK, 0 rows affected (0.04 sec)
```



