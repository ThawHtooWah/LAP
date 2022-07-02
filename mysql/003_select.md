### MYSQL SELECT 
> How to search records from a table
### **3.1 MYSQL SELECT**
#### **Search all columns**
```sql
SELECT * FROM table_name;
```
```sql
SELECT * FROM Girls;
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
|    2 | Betty | Betty2B |
+------+-------+---------+
2 rows in set (0.00 sec)
```
#### **Search specific columns**
```sql
SELECT column1, column FROM table_name;
```
```sql
SELECT No, Name FROM Girls;
+------+-------+
| No   | Name  |
+------+-------+
|    1 | Alica |
|    2 | Betty |
+------+-------+
2 rows in set (0.00 sec)
```
#### **Search with alias field names**
```sql
SELECT column_name AS alias_name FROM table_name;
```
```sql
SELECT Name AS girls_name FROM Girls;
+------------+
| girls_name |
+------------+
| Alica      |
| Betty      |
+------------+
2 rows in set (0.00 sec)
```

### **3.2 MYSQL SELECT with WHERE clause**
```sql
SELECT * FROM table_name WHERE condition;
```
```sql
SELECT * FROM Girls WHERE Name = 'Alica';
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
+------+-------+---------+
1 row in set (0.00 sec)
```

### **3.3 MYSQL SELECT with logical operators**
#### **Search with AND operator**
```sql
SELECT * FROM table_name WHERE condition AND condition;
```
```sql
SELECT * FROM Girls WHERE No = 1 AND Name = 'Alica';
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
+------+-------+---------+
1 row in set (0.00 sec)
```
#### **Search with OR operator**
```sql
SELECT * FROM table_name WHERE condition OR condition;
```
```sql
SELECT * FROM Girls WHERE No = 1 OR Name = 'Betty';
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
|    2 | Betty | Betty2B |
+------+-------+---------+
2 rows in set (0.00 sec)
```
### **3.4 MYSQL SELECT with IN/ NOT IN Keywords**
#### **Search with IN Keyword**
```sql
SELECT * FROM table_name WHERE table_name IN (...);
```
```sql
SELECT * FROM Girls WHERE No IN (1,2);
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
|    2 | Betty | Betty2B |
+------+-------+---------+
2 rows in set (0.00 sec)
```
#### **Search with NOT IN Keyword**
```sql
SELECT * FROM table_name WHERE table_name NOT IN (...);
```
```sql
SELECT * FROM Girls WHERE No NOT IN (1);
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    2 | Betty | Betty2B |
+------+-------+---------+
1 row in set (0.00 sec)
```
### **3.5 MYSQL SELECT with comparison operators**
#### **Search with = Equal Operator**
```sql
SELECT * FROM table_name WHERE column_name = value;
```
```sql
SELECT * FROM Girls WHERE Name = 'Betty';
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    2 | Betty | Betty2B |
+------+-------+---------+
1 row in set (0.00 sec)
```
#### **Search with > greater than Operator**
```sql
SELECT * FROM table_name WHERE column_name > value;
```
```sql
SELECT * FROM Girls WHERE No > 1;
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    2 | Betty | Betty2B |
+------+-------+---------+
1 row in set (0.00 sec)
```
#### **Search with < greater than Operator**
```sql
SELECT * FROM table_name WHERE column_name < value;
```
```sql
SELECT * FROM Girls WHERE No < 2;
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    1 | Alica | Alice1A |
+------+-------+---------+
1 row in set (0.00 sec)
```
#### **Search with <> or != not equal Operator**
```sql
SELECT * FROM table_name WHERE column_name <> value;
(or)
SELECT * FROM table_name WHERE column_name != value;
```
```sql
SELECT * FROM Girls WHERE No <>1;
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    2 | Betty | Betty2B |
+------+-------+---------+
1 row in set (0.00 sec)

(or)

SELECT * FROM Girls WHERE No != 1;
+------+-------+---------+
| No   | Name  | Nric    |
+------+-------+---------+
|    2 | Betty | Betty2B |
+------+-------+---------+
1 row in set (0.00 sec)
```


