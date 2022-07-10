### SUB-QUERIES
> To return data that will be used in the main query as a condition to further restrict the data to be retrieved.  
> Sub-queries can be used with the SELECT, INSERT, UPDATE, and DELETE statements.

```sql
SELECT * FROM employees ORDER BY id;
+----+--------+------------+
| id | name   | address    |
+----+--------+------------+
|  1 | John   | Insein     |
|  2 | Smith  | Mayangone  |
|  3 | Mark   | Hlaing     |
|  4 | Dee    | Botahtaung |
|  5 | Ron    | Hlaing     |
|  6 | Rose   | Mayangone  |
|  7 | Cherry | Hlaing     |
+----+--------+------------+

SELECT * FROM employments ORDER BY employee_id;
+-------------+------------+-------------------+-----------+-------------+
| employee_id | department | position          | salary    | joined_date |
+-------------+------------+-------------------+-----------+-------------+
|           1 | IT         | IT Engineer       | 100000.50 | 2012-01-01  |
|           2 | HR         | HR Manager        | 100000.00 | 2011-09-13  |
|           3 | Admin      | Admin Manager     |  60000.00 | 2016-01-01  |
|           4 | IT         | PHP Developer     | 200000.00 | 2016-12-01  |
|           5 | IT         | Reporting Analyst | 100000.00 | 2022-05-01  |
|           6 | HR         | HR Officer        |  70000.00 | 2021-11-30  |
|           7 | Admin      | Admin Officer     |  60000.00 | 2021-05-17  |
+-------------+------------+-------------------+-----------+-------------+
```
#### **13.1 Sub-Query with SELECT**
```sql
SELECT * FROM employees 
WHERE id in
(
  SELECT employee_id FROM employments
  WHERE department = 'IT'
);

+----+------+------------+
| id | name | address    |
+----+------+------------+
|  1 | John | Insein     |
|  4 | Dee  | Botahtaung |
|  5 | Ron  | Hlaing     |
+----+------+------------+
```
#### **13.2 Sub-Query with INSERT**
> Assume that the company is going to give bonus (10000) to old employees who started joining the company before 2017.
```sql
-- First, create bonus table
CREATE TABLE bonus_achievements
(
  bonus_date date,
  employee_id int,
  amount decimal(10,2)
);

-- SubQuery with INSERT
INSERT INTO bonus_achievements 
SELECT current_date as bonus_date,
id as employee_id,
10000 as amount
FROM employees 
WHERE id in
(
  SELECT employee_id FROM employments
  WHERE joined_date <= '2016-12-31'
);

+------------+-------------+----------+
| bonus_date | employee_id | amount   |
+------------+-------------+----------+
| 2022-07-10 |           1 | 10000.00 |
| 2022-07-10 |           2 | 10000.00 |
| 2022-07-10 |           3 | 10000.00 |
| 2022-07-10 |           4 | 10000.00 |
+------------+-------------+----------+
```

#### **13.3 Sub-Query with UPDATE**
> Assume that the company is going to give double bonus (20000) to old premium employees who started joining the company since 2011

```sql
UPDATE bonus_achievements
SET amount = amount * 2
WHERE employee_id in
(
  SELECT employee_id FROM employments
  WHERE year(joined_date) = 2011
);

+------------+-------------+----------+
| bonus_date | employee_id | amount   |
+------------+-------------+----------+
| 2022-07-10 |           1 | 10000.00 |
| 2022-07-10 |           2 | 20000.00 |
| 2022-07-10 |           3 | 10000.00 |
| 2022-07-10 |           4 | 10000.00 |
+------------+-------------+----------+
```

#### **13.4 Sub-Query with DELETE**
> Assume that the company is going to redue new staffs who joined this year.

```sql
DELETE FROM employees
WHERE id in
(
  SELECT employee_id FROM employments
  WHERE year(joined_date) = 2022
);
+----+--------+------------+
| id | name   | address    |
+----+--------+------------+
|  1 | John   | Insein     |
|  2 | Smith  | Mayangone  |
|  3 | Mark   | Hlaing     |
|  4 | Dee    | Botahtaung |
|  6 | Rose   | Mayangone  |
|  7 | Cherry | Hlaing     |
+----+--------+------------+

DELETE FROM employments
WHERE employee_id in
(
  SELECT employee_id FROM employments
  WHERE year(joined_date) = 2022
);
+-------------+------------+---------------+-----------+-------------+
| employee_id | department | position      | salary    | joined_date |
+-------------+------------+---------------+-----------+-------------+
|           1 | IT         | IT Engineer   | 100000.50 | 2012-01-01  |
|           2 | HR         | HR Manager    | 100000.00 | 2011-09-13  |
|           3 | Admin      | Admin Manager |  60000.00 | 2016-01-01  |
|           4 | IT         | PHP Developer | 200000.00 | 2016-12-01  |
|           6 | HR         | HR Officer    |  70000.00 | 2021-11-30  |
|           7 | Admin      | Admin Officer |  60000.00 | 2021-05-17  |
+-------------+------------+---------------+-----------+-------------+
```
