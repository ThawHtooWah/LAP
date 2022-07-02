### AGGREGATE FUNCTIONS
> Performing calculations on multiple rows Of a single column of a table And returning a single value.  
>SUM, AVG, MAX, MIN , COUNT, DISTINCT

```sql
SELECT * FROM transactions order by 1;
+----+-------------+--------+----------+------------------+
| id | customer_id | amount | category | notes            |
+----+-------------+--------+----------+------------------+
|  1 |           2 |  10000 | TRANSFER | to 09xxxxxxx     |
|  2 |           1 |   3000 | TOPUP    | to 09xxxxxxx     |
|  3 |           1 |   5000 | PURCHASE | netflix card     |
|  4 |           2 |   5000 | PURCHASE | apple music card |
|  5 |           1 |   1000 | TOPUP    | to 09xxxxxxx     |
|  6 |           1 |   3000 | TOPUP    | to 09xxxxxxx     |
|  7 |           2 |   3000 | TOPUP    | to 09xxxxxxx     |
|  8 |           2 |  10000 | TRANSFER | to 09xxxxxxx     |
|  9 |           2 |   1000 | TOPUP    | to 09xxxxxxx     |
+----+-------------+--------+----------+------------------+
```
#### **12.1 SUM , AVG**
```sql
SELECT SUM(amount) AS total_amount, AVG(amount) AS average_amount FROM transactions;

+--------------+----------------+
| total_amount | average_amount |
+--------------+----------------+
|        41000 |      4555.5556 |
+--------------+----------------+
```

#### **12.2 MIN, MAX**
```sql
SELECT MIN(amount) AS min_amount, MAX(amount) AS max_amount FROM transactions;

+------------+------------+
| min_amount | max_amount |
+------------+------------+
|       1000 |      10000 |
+------------+------------+

```

#### **12.3 DISTINCT**
```sql
SELECT DISTINCT category AS unique_categories FROM transactions;

+-------------------+
| unique_categories |
+-------------------+
| PURCHASE          |
| TOPUP             |
| TRANSFER          |
+-------------------+

```

#### **12.4 Count(*) , COUNT DISTINCT**
```sql
SELECT COUNT(*) AS all_record_count, COUNT(DISTINCT category) AS unique_categories_count FROM transactions;

+------------------+-------------------------+
| all_record_count | unique_categories_count |
+------------------+-------------------------+
|                9 |                       3 |
+------------------+-------------------------+

```