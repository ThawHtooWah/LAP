### MYSQL SELECT 
> How to search records from a table
#### **Search all columns**
```sql
SELECT * FROM table_name;
```
```sql
mysql> SELECT * FROM Girls;
```
#### **Search specific columns**
```sql
SELECT column1, column FROM table_name;
```
```sql
mysql> SELECT No, Name FROM Girls;
```
#### **Search with alias field names**
```sql
SELECT column_name AS alias_name FROM table_name;
```
```sql
mysql> SELECT Name AS girls_name FROM Girls;
```

### MYSQL SELECT with WHERE clause 
```sql
SELECT * FROM table_name WHERE condition;
```
```sql
mysql> SELECT * FROM Girls WHERE Name = 'Ann';
```

### MYSQL SELECT with logical operators
#### **Search with AND operator**
```sql
SELECT * FROM table_name WHERE condition AND condition;
```
```sql
mysql> SELECT * FROM Girls WHERE No = 10 AND Name = 'Ann';
```
#### **Search with OR operator**
```sql
SELECT * FROM table_name WHERE condition OR condition;
```
```sql
mysql> SELECT * FROM Girls WHERE No = 10 OR Name = 'Bibo';
```
### MYSQL SELECT with IN/ NOT IN Keywords
#### **Search with IN Keyword**
```sql
SELECT * FROM table_name WHERE table_name NOT IN (...);
```
```sql
mysql> SELECT * FROM Girls WHERE No NOT IN (1,2,3);
```



