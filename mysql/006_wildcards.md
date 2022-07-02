### MYSQL WILDCARDS
> How to search and match the data using the operator LIKE and NOT LIKE

```sql
SELECT *  FROM Students;
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          2 | John         | 2022-06-02 | NULL            |
|          3 | Smith        | 2022-06-03 | NULL            |
|          4 | Ann          | 2022-06-04 | ann@gmail.com   |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
+------------+--------------+------------+-----------------+
```

#### **6.1 % the percentage (% stands for any number or character count)**
##### Start with search key
```sql
SELECT * FROM table_name WHERE column_name LIKE 'search_key%';
```
```sql
SELECT *  FROM Students WHERE student_name LIKE 'Jo%';
+------------+--------------+------------+-------+
| student_id | student_name | date       | email |
+------------+--------------+------------+-------+
|          2 | John         | 2022-06-02 | NULL  |
+------------+--------------+------------+-------+
```

##### End with search key
```sql
SELECT * FROM table_name WHERE column_name LIKE '%search_key';
```
```sql
SELECT *  FROM Students WHERE student_name NOT LIKE '%n';
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          3 | Smith        | 2022-06-03 | NULL            |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
+------------+--------------+------------+-----------------+
```

#### **6.2 _ underscore wildcard ( 1 _ for 1 char/number count, 2 __ for 2 char/number counts, ...)**
##### Start with search key with 2 places after
```sql
SELECT * FROM table_name WHERE column_name LIKE 'searchkey__';
```
```sql
SELECT *  FROM Students WHERE student_name LIKE 'Wil__';
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
+------------+--------------+------------+-----------------+
```

##### Not End with search key with 1 place before
```sql
SELECT * FROM table_name WHERE column_name NOT LIKE '_searchkey';
```
```sql
SELECT *  FROM Students WHERE student_name NOT LIKE '_nn';
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          2 | John         | 2022-06-02 | NULL            |
|          3 | Smith        | 2022-06-03 | NULL            |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
+------------+--------------+------------+-----------------+
```
