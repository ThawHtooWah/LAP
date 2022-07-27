### MYSQL INSERT INTO TABLE
> How to insert records into a table
#### **2.1 Insert into table**
```sql
INSERT INTO table_name(column_1,column_2,...) VALUES (value_1,value_2,...);
```
```sql
INSERT INTO Girls VALUES (1, 'Alica', 'Alice1A');
```
  (or)
```sql
INSERT INTO Girls(No, Name, Nric) VALUES (2,'Betty','Betty2B');
```
  (or)
```sql
INSERT INTO Girls VALUES 
(3,'Cindy','Cindy3C'), 
(4,'Dolly','Dolly4D'), 
(5,'Emmy','Emmy5E'), 
(6,'Emmy','Emmy6E'), 
(7,'Amy','Amy7A'), 
(8,'Elizabeth','Elizabeth8E'), 
(9,'Bibo','Bibo9B'), 
(10,'Ann','Ann10A');
```

#### **2.2 Last Insert ID**
```sql
select * from Students;
+------------+--------------+------------+-----------------+
| student_id | student_name | date       | email           |
+------------+--------------+------------+-----------------+
|          1 | tt           | 2022-06-01 | tt@gmail.com    |
|          2 | John         | 2022-06-02 | NULL            |
|          3 | Smith        | 2022-06-03 | NULL            |
|          4 | Ann          | 2022-06-04 | ann@gmail.com   |
|          5 | WIlly        | 2022-06-05 | willy@gmail.com |
+------------+--------------+------------+-----------------+

INSERT INTO Students(student_name, date) VALUES ('Zan', '2022-06-20');
Query OK, 1 row affected (0.04 sec)

select last_insert_id();
+------------------+
| last_insert_id() |
+------------------+
|                6 |
+------------------+
1 row in set (0.00 sec)
```
