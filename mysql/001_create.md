### MYSQL CREATE database/ table
> How to create databases and tables
#### **1.1 Create Database**
```sql
CREATE DATABASE database_name;
```
```sql
CREATE DATABASE my_db;
Query OK, 1 row affected (0.03 sec)
```

#### **1.2 Show Databases**
```sql
SHOW DATABASES;
```
```sql
SHOW DATABASES;
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

#### **1.3 Drop Database**
```sql
DROP DATABASE database_name;
```
```sql
DROP DATABASE my_db;
Query OK, 0 rows affected (0.05 sec)
```

#### **1.4 Use Database**
```sql
USE database_name
```
```sql
USE my_db
Database changed
```

#### **1.5 Create Table**
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
#### **1.6 Show Tables**
```sql
SHOW TABLES;
```
```sql
SHOW TABLES;
+-----------------+
| Tables_in_my_db |
+-----------------+
| Girls           |
| students        |
+-----------------+
2 rows in set (0.00 sec)
```

#### **1.7 Explain/Describe Table**
```sql
DESCRIBE table_name;
(or)
DESC table_name;
(or)
EXPLAIN table_name;
```
```sql
DESCRIBE students;
(or)
DESC students;
(or)
EXPLAIN students;
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)
```

#### **1.8 Not Null**
```sql
CREATE TABLE employees
(
  id int PRIMARY KEY, 
  name varchar(100) NOT NULL, 
  address varchar(100)
);

CREATE TABLE employments
(
  employee_id int PRIMARY KEY, 
  department varchar(100) NOT NULL, 
  position varchar(100), 
  salary decimal(10,2), 
  joined_date date NOT NULL
);  
```


