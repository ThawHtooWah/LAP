### MYSQL SELECT 
> How to search records from a table
#### **Search all columns**
```sql
SELECT * FROM table_name;
```
```sql
SELECT * FROM Girls;
```
#### **Search specific columns**
```sql
SELECT column1, column FROM table_name;
```
```sql
SELECT No, Name FROM Girls;
```
#### **Search with alias field names**
```sql
SELECT column_name AS alias_name FROM table_name;
```
```sql
SELECT Name AS girls_name FROM Girls;
```
