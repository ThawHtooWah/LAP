### MYSQL UPDATE and DELETE
> How to update/delete records from a table and how to delete(drop) a table
#### **4.1 Update a record from a table**
```sql
UPDATE table_name SET column_name = new_value WHERE condition;
```
```sql
UPDATE Girls SET Name = 'Alice' WHERE Name = 'Alica';
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

#### **4.2 Delete a record from a table**
```sql
DELETE FROM table_name WHERE condition;
```
```sql
DELETE FROM Girls WHERE Name = 'Alice';
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

#### **4.3 Delete (Drop) a table**
```sql
DROP TABLE table_name;
```
```sql
DROP TABLE Girls;
Query OK, 0 rows affected (0.04 sec)
```

#### **4.4 Delete all records from a table**
```sql
TRUNCATE TABLE table_name;
```
```sql
TRUNCATE TABLE Girls;
Query OK, 0 rows affected (0.07 sec)

SELECT * FROM Girls;
Empty set (0.00 sec)
```

