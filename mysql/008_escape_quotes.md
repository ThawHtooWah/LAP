### MYSQL ESCAPTE QUOTES
> How to escapte single quote ' and double quotes '' in queries

#### **8.1 Single Quote**
```sql
INSERT INTO Students VALUES (7, 'Thaws\'' , '2022-01-01', 'thaws@gmail.com');
```
```
SELECT * FROM Students;
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          2 | John         | 2022-06-02 | NULL            |
|          3 | Smith        | 2022-06-03 | NULL            |
|          4 | Ann          | 2022-06-04 | ann@gmail.com   |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
|          6 | Zan          | 2022-06-20 | NULL            |
|          7 | Thaws'       | 2022-01-01 | thaws@gmail.com |
+------------+--------------+------------+-----------------+
7 rows in set (0.00 sec)
```

#### **8.2 Double Quotes**
```sql
UPDATE Students SET student_name = 'Thaws\"' WHERE student_name = 'Thaws\'';
```
```
SELECT * FROM Students;
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          2 | John         | 2022-06-02 | NULL            |
|          3 | Smith        | 2022-06-03 | NULL            |
|          4 | Ann          | 2022-06-04 | ann@gmail.com   |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
|          6 | Zan          | 2022-06-20 | NULL            |
|          7 | Thaws"       | 2022-01-01 | thaws@gmail.com |
+------------+--------------+------------+-----------------+
7 rows in set (0.00 sec)
