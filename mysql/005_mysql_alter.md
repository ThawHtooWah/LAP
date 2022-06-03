### MYSQL ALTER
> How to add column, delete column, change data type to a table, and how to rename a table.
#### **5.1 ADD Columm**
```sql
ALTER TABLE table_name ADD COLUMN column_name data_type AFTER column_name;
```
```sql
mysql> ALTER TABLE students
    -> ADD COLUMN email VARCHAR(20)
    -> AFTER student_name;

-- Before
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+

-- After
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| email        | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+
```

#### **5.2 DELETE Columm**
```sql
ALTER TABLE table_name DROP COLUMN column_name;
```
```sql
mysql> ALTER TABLE students
    -> DROP COLUMN email;

-- Before
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| email        | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+

-- After
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+
```

#### **5.3 CHANGE Columm Data Type**
```sql
ALTER TABLE table_name CHANGE COLUMN old_column_name new_column_name data_type;
```
```sql
mysql> ALTER TABLE students 
    -> CHANGE student_name 
    -> student_name varchar(100);

-- Before
+--------------+-------------+------+-----+---------+----------------+
| Field        | Type        | Null | Key | Default | Extra          |
+--------------+-------------+------+-----+---------+----------------+
| student_id   | int         | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(20) | YES  |     | NULL    |                |
| date         | date        | YES  |     | NULL    |                |
+--------------+-------------+------+-----+---------+----------------+

-- After 
+--------------+--------------+------+-----+---------+----------------+
| Field        | Type         | Null | Key | Default | Extra          |
+--------------+--------------+------+-----+---------+----------------+
| student_id   | int          | NO   | PRI | NULL    | auto_increment |
| student_name | varchar(100) | YES  |     | NULL    |                |
| date         | date         | YES  |     | NULL    |                |
+--------------+--------------+------+-----+---------+----------------+

```

