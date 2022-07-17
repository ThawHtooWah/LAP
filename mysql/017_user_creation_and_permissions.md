## USER CREATION AND GRANT PERMISSIONS
> Create users and set different authorized access between users.

### 17.1 List User
```sql
SELECT user FROM mysql.user;
+------------------+
| user             |
+------------------+
| mysql.infoschema |
| mysql.session    |
| mysql.sys        |
| root             |
+------------------+
```

### 17.2 Create User
```sql
CREATE USER 'username'@'hostname' IDENTIFIED BY 'password';
```
```sql
CREATE USER 'user1'@'localhost' IDENTIFIED BY 'user1password';

-- List Users
mysql> SELECT user FROM mysql.user;
+------------------+
| user             |
+------------------+
| bookstack        |
| debian-sys-maint |
| mysql.infoschema |
| mysql.session    |
| mysql.sys        |
| root             |
| user1            |
+------------------+
```
**Log in with user1** 
- using xampp
  ```sh
  :\>XAMPP\mysql\bin\mysql.exe –uuser1 -p 
  ```
- using mysql
  ```sh
  mysql -h localhost -u user1 -p
  ```
**After login with user1**
```sql 
mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
+--------------------+
```

### 17.3 Grant Permission
> Types of Permissions
> - CREATE / INSERT / SELECT / UPDATE / DELETE
> - ALL
```sql
GRANT type_of_permission PRIVILEGES ON database.table TO 'username'@'hostname';
```
#### 17.3.1 Grant SELECT Permission
> Assume as giving **SELECT** access to **employees** table of **lap3** database on **user1**

```sql 
-- Grant Access
GRANT SELECT ON lap3.employees TO 'user1'@'localhost';
```

```sql
-- Before giving SELECT access logged in with user1
mysql> SELECT * FROM employees;
ERROR 1142 (42000): SELECT command denied to user 'user1'@'localhost' for table 'employees'

-- After giving SELECT access logged in with user1
mysql> SELECT * FROM employees;
+----+--------+------------+
| id | name   | address    |
+----+--------+------------+
|  1 | John   | Insein     |
|  2 | Smith  | Mayangone  |
|  3 | Mark   | Hlaing     |
|  4 | Dee    | Botahtaung |
|  6 | Rose   | Mayangone  |
|  7 | Cherry | Hlaing     |
|  8 | Bee    | Insein     |
+----+--------+------------+
```
#### 17.3.2 Grant ALL Permission
```sql
GRANT ALL PRIVILEGES ON *.* TO 'user1'@'localhost';
```

### 17.4 Drop Permission
```sql 
-- Grant Access
REVOKE SELECT ON lap3.employees FROM 'user1'@'localhost';
```

```sql
-- Before dropping SELECT access logged in with user1
mysql> SELECT * FROM employees;
+----+--------+------------+
| id | name   | address    |
+----+--------+------------+
|  1 | John   | Insein     |
|  2 | Smith  | Mayangone  |
|  3 | Mark   | Hlaing     |
|  4 | Dee    | Botahtaung |
|  6 | Rose   | Mayangone  |
|  7 | Cherry | Hlaing     |
|  8 | Bee    | Insein     |
+----+--------+------------+

-- After dropping SELECT access logged in with user1
mysql> SELECT * FROM employees;
ERROR 1142 (42000): SELECT command denied to user 'user1'@'localhost' for table 'employees'
```