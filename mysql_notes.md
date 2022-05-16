### MYSQL CREATE database/ table
> How to create databases and tables
#### **Create Database**
```sql
CREATE DATABASE database_name;
```
```sql
mysql> CREATE DATABASE my_db;
Query OK, 1 row affected (0.03 sec)
```

#### **Show Databases**
```sql
SHOW DATABASES;
```
```sql
mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| my_db              |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
6 rows in set (0.00 sec)
```

#### **Drop Database**
```sql
DROP DATABASE database_name;
```
```sql
mysql> DROP DATABASE my_db;
Query OK, 0 rows affected (0.05 sec)
```

#### **Use Database**
```sql
USE database_name
```
```sql
mysql> USE my_db
Database changed
```

#### **Create Table**
```sql
CREATE TABLE table_name
(
  field_name data_type
);
```
```sql
--example 1 
CREATE TABLE Girls
(
  No Numeric, 
  Name text, 
  Nric text
);

--example 2
CREATE TABLE students
(
  student_id INT AUTO_INCREMENT PRIMARY KEY,
  student_name VARCHAR(20),
  date DATE
);
```

### MYSQL INSERT INTO TABLE
> How to insert records into a table
#### **Insert into table**
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
