### MYSQL LIMIT, OFFSET
> The LIMIT keyword is used to limit the number of rows returned in a query result.  
> The OFF SET value allows us to specify which row to start from retrieving data

#### **9.1 LIMIT**
```sql
SELECT * FROM Students LIMIT 1;
+------------+--------------+------------+--------------+
| student_id | student_name | date       | email        |
+------------+--------------+------------+--------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com |
+------------+--------------+------------+--------------+
```

#### **9.2 OFFSET**
```sql
SELECT * FROM Students LIMIT 1 OFFSET 2;
+------------+--------------+------------+-------+
| student_id | student_name | date       | email |
+------------+--------------+------------+-------+
|          3 | Smith        | 2022-06-03 | NULL  |
+------------+--------------+------------+-------+

(OR)

SELECT * FROM Students LIMIT 2,1;
+------------+--------------+------------+-------+
| student_id | student_name | date       | email |
+------------+--------------+------------+-------+
|          3 | Smith        | 2022-06-03 | NULL  |
+------------+--------------+------------+-------+
```