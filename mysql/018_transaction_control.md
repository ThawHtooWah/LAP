## TRANSACTION CONTROL
> - **COMMIT** − to save the changes.
> - **ROLLBACK** − to roll back the changes.
> - **SAVEPOINT** − creates points within the groups of transactions in which to ROLLBACK.
> - **SET TRANSACTION** − Places a name on a transaction.

### 17.1 Commit
**Initiate Transaction**
```sql 
mysql> START TRANSACTION;

mysql> SELECT * FROM employees;
+----+--------+-----------+
| id | name   | address   |
+----+--------+-----------+
|  6 | Rose   | Mayangone |
|  7 | Cherry | Hlaing    |
|  8 | Bee    | Insein    |
+----+--------+-----------+
```
**Transaction Action**
```sql
mysql> DELETE FROM employees where id = 6;

mysql> SELECT * FROM employees;
+----+--------+-----------+
| id | name   | address   |
+----+--------+-----------+
|  7 | Cherry | Hlaing    |
|  8 | Bee    | Insein    |
+----+--------+-----------+
```
**Commit**
```sql
mysql> COMMIT;

mysql> SELECT * FROM employees;
+----+--------+---------+
| id | name   | address |
+----+--------+---------+
|  7 | Cherry | Hlaing  |
|  8 | Bee    | Insein  |
+----+--------+---------+
```

### 17.2 Rollback
**Initiate Transaction**
```sql 
mysql> START TRANSACTION;

mysql> SELECT * FROM employees;
+----+--------+-----------+
| id | name   | address   |
+----+--------+-----------+
|  7 | Cherry | Hlaing    |
|  8 | Bee    | Insein    |
+----+--------+-----------+
```
**Transaction Action**
```sql
mysql> DELETE FROM employees where id = 7;

mysql> SELECT * FROM employees;
+----+------+---------+
| id | name | address |
+----+------+---------+
|  8 | Bee  | Insein  |
+----+------+---------+
```
**Rollback**
```sql
mysql> ROLLBACK;

mysql> SELECT * FROM employees;
+----+--------+---------+
| id | name   | address |
+----+--------+---------+
|  7 | Cherry | Hlaing  |
|  8 | Bee    | Insein  |
+----+--------+---------+
```
### 17.3 Savepoint
**Initiate Transaction**
```sql 
mysql> START TRANSACTION;

mysql> SELECT * FROM employees;
+----+--------+-----------+
| id | name   | address   |
+----+--------+-----------+
|  7 | Cherry | Hlaing    |
|  8 | Bee    | Insein    |
+----+--------+-----------+
```
**Create Savepoint**
```sql
mysql> SAVEPOINT SP1;
```
**Transaction Action**
```sql
mysql> INSERT INTO employees VALUES (10,'Thaw', 'Insein');

mysql> SELECT * FROM employees;
+----+--------+---------+
| id | name   | address |
+----+--------+---------+
|  7 | Cherry | Hlaing  |
|  8 | Bee    | Insein  |
| 10 | Thaw   | Insein  |
+----+--------+---------+
``` 
**Rollback to Savepoint**
```sql
mysql> ROLLBACK TO SP1;

mysql> SELECT * FROM employees;
+----+--------+---------+
| id | name   | address |
+----+--------+---------+
|  7 | Cherry | Hlaing  |
|  8 | Bee    | Insein  |
+----+--------+---------+
```
**Drop Savepoint**
```sql
mysql> RELEASE SAVEPOINT SP1;
```

### 18.4 Set Transaction
> - READ ONLY
> - READ WRITE

**Read Only**
```sql
mysql> SET TRANSACTION READ ONLY;

mysql> START TRANSACTION;

mysql> SELECT * FROM employees;
+----+--------+---------+
| id | name   | address |
+----+--------+---------+
|  7 | Cherry | Hlaing  |
|  8 | Bee    | Insein  |
+----+--------+---------+

mysql> DELETE FROM employees WHERE id = 7;
ERROR 1792 (25006): Cannot execute statement in a READ ONLY transaction.

mysql> COMMIT;
```

**Read Write**
```sql
mysql> SET TRANSACTION READ WRITE;

mysql> START TRANSACTION;

mysql> DELETE FROM employees WHERE id = 7;

mysql> SELECT * FROM employees;
+----+------+---------+
| id | name | address |
+----+------+---------+
|  8 | Bee  | Insein  |
+----+------+---------+
```