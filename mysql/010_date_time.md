### MYSQL DATE, TIME, DATETIME
#### **10.1 Current Date and Time**
- NOW() and CURRENT_TIMESTAMP() are the same.
```sql
SELECT NOW(), CURRENT_TIMESTAMP();
+---------------------+---------------------+
| NOW()               | CURRENT_TIMESTAMP() |
+---------------------+---------------------+
| 2022-07-02 20:56:00 | 2022-07-02 20:56:00 |
+---------------------+---------------------+
```

- CURDATE() and CURRENT_DATE() are the same.
```sql
SELECT CURDATE(), CURRENT_DATE();
+------------+----------------+
| CURDATE()  | CURRENT_DATE() |
+------------+----------------+
| 2022-07-02 | 2022-07-02     |
+------------+----------------+
```

- CURTIME() and CURRENT_TIME() are the same.
```sql
SELECT CURTIME(), CURRENT_TIME();
+-----------+----------------+
| CURTIME() | CURRENT_TIME() |
+-----------+----------------+
| 20:56:00  | 20:56:00       |
+-----------+----------------+
```

#### **10.1 Day, Week, Month, Year**
```sql
SELECT DAY(NOW()) AS day_of_month,
WEEK(NOW()) AS week_of_year, 
MONTH(NOW()) AS month_of_year,
YEAR(NOW()) AS year;
+--------------+--------------+---------------+------+
| day_of_month | week_of_year | month_of_year | year |
+--------------+--------------+---------------+------+
|            2 |           26 |             7 | 2022 |
+--------------+--------------+---------------+------+
```