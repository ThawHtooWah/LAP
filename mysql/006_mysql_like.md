### MYSQL LIKE
> How to search and match the data using the operator LIKE and NOT LIKE
#### **6.1 Starts with something**
```sql
SELECT * FROM table_name WHERE column_name LIKE 'search_key%';
```
```sql
mysql> SELECT *  FROM Students WHERE student_name LIKE 'Jo%';
+------------+--------------+------------+----------------+
| student_id | student_name | date       | email          |
+------------+--------------+------------+----------------+
|          2 | John         | 2022-06-06 | john@gmail.com |
+------------+--------------+------------+----------------+
1 row in set (0.00 sec)
```
