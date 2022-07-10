### AGGREGATIONS
> Get the results into grouping using aggregate functions.


```sql
mysql> SELECT * FROM employments;
+-------------+------------+---------------+-----------+-------------+
| employee_id | department | position      | salary    | joined_date |
+-------------+------------+---------------+-----------+-------------+
|           1 | IT         | IT Engineer   | 100000.50 | 2012-01-01  |
|           2 | HR         | HR Manager    | 100000.00 | 2011-09-13  |
|           3 | Admin      | Admin Manager |  60000.00 | 2016-01-01  |
|           4 | IT         | PHP Developer | 200000.00 | 2016-12-01  |
|           6 | HR         | HR Officer    |  70000.00 | 2021-11-30  |
|           7 | Admin      | Admin Officer |  60000.00 | 2021-05-17  |
|           9 | IT         | Web Developer | 100000.00 | 2021-07-05  |
+-------------+------------+---------------+-----------+-------------+
```

#### **15.1 Aggregation with IF**
> IF (condition , true, false)
```sql
SELECT 
SUM(IF(department = 'IT', salary, 0)) AS "Pay for IT",
SUM(IF(department = 'Admin', salary, 0)) AS "Pay for Admin",
SUM(IF(department = 'HR', salary, 0)) AS "Pay for HR"
FROM employments;

+------------+---------------+------------+
| Pay for IT | Pay for Admin | Pay for HR |
+------------+---------------+------------+
|  400000.50 |     120000.00 |  170000.00 |
+------------+---------------+------------+
```

#### **15.2 Aggregation with Aggregate Functions using GROUP BY**
```sql
SELECT 
department, 
COUNT(*) employee_count, 
SUM(salary) AS total_pays
FROM employments
GROUP BY department;

+------------+----------------+------------+
| department | employee_count | total_pays |
+------------+----------------+------------+
| IT         |              3 |  400000.50 |
| HR         |              2 |  170000.00 |
| Admin      |              2 |  120000.00 |
+------------+----------------+------------+
```

#### **15.3 Aggregation using HAVING**
```sql 
SELECT 
department, 
COUNT(*) employee_count, 
SUM(salary) AS total_pays
FROM employments
GROUP BY department
HAVING COUNT(*) > 2;

+------------+----------------+------------+
| department | employee_count | total_pays |
+------------+----------------+------------+
| IT         |              3 |  400000.50 |
+------------+----------------+------------+
```