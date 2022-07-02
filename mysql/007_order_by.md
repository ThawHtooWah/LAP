### MYSQL ORDER BY
> How to sort records in ascending and descending order by the column

#### **7.1 Ascending Order (DEFAULT)**
```sql
SELECT * FROM table_name ORDER BY column_name;
```
```sql
SELECT * FROM Students ORDER BY student_name;
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          4 | Ann          | 2022-06-04 | ann@gmail.com   |
|          2 | John         | 2022-06-02 | NULL            |
|          3 | Smith        | 2022-06-03 | NULL            |
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
|          6 | Zan          | 2022-06-20 | NULL            |
+------------+--------------+------------+-----------------+
```

#### **7.2 Descending Order**

```sql
SELECT * FROM table_name ORDER BY column_name DESC;
```
```sql
SELECT * FROM Students ORDER BY student_id DESC;
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          6 | Zan          | 2022-06-20 | NULL            |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
|          4 | Ann          | 2022-06-04 | ann@gmail.com   |
|          3 | Smith        | 2022-06-03 | NULL            |
|          2 | John         | 2022-06-02 | NULL            |
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
+------------+--------------+------------+-----------------+
```