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
#### **Show Tables**
```sql
SHOW TABLES;
```
```sql
mysql> SHOW TABLES;
+-----------------+
| Tables_in_my_db |
+-----------------+
| Girls           |
| students        |
+-----------------+
2 rows in set (0.00 sec)
```

#### **Explain/Describe Table**
```sql
DESCRIBE table_name;
(or)
DESC table_name;
(or)
EXPLAIN table_name;
```
```sql
mysql> DESCRIBE students;
(or)
mysql> DESC students;
(or)
mysql> EXPLAIN students;
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)
```
