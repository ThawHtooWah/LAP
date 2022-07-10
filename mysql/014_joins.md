### Joins
> - INNER JOIN 
> - LEFT JOIN 
> - RIGHT JOIN  
> - FULL JOIN


```sql
SELECT * FROM employees ORDER BY id;
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

SELECT * FROM employments ORDER BY employee_id;
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
#### **14.1 INNER JOIN**
> (INNER) JOIN: Select records that have matching values in both tables.

```sql
SELECT employments.employee_id,
employees.name as employee_name,
employments.position as employee_position
FROM employees 
INNER JOIN employments ON employments.employee_id = employees.id;

(or)

SELECT 
b.employee_id, 
a.name as employee_name, 
b.position as employee_position 
FROM employees a 
INNER JOIN employments b ON b.employee_id = a.id;

+-------------+---------------+-------------------+
| employee_id | employee_name | employee_position |
+-------------+---------------+-------------------+
|           1 | John          | IT Engineer       |
|           2 | Smith         | HR Manager        |
|           3 | Mark          | Admin Manager     |
|           4 | Dee           | PHP Developer     |
|           6 | Rose          | HR Officer        |
|           7 | Cherry        | Admin Officer     |
+-------------+---------------+-------------------+
```

#### **14.2 LEFT JOIN**
> LEFT (OUTER) JOIN: Select records from the first (left-most) table with matching right table records.  
```sql
SELECT 
b.employee_id, 
a.name as employee_name, 
b.position as employee_position 
FROM employees a 
LEFT JOIN employments b ON b.employee_id = a.id; 

+-------------+---------------+-------------------+
| employee_id | employee_name | employee_position |
+-------------+---------------+-------------------+
|           1 | John          | IT Engineer       |
|           2 | Smith         | HR Manager        |
|           3 | Mark          | Admin Manager     |
|           4 | Dee           | PHP Developer     |
|           6 | Rose          | HR Officer        |
|           7 | Cherry        | Admin Officer     |
|        NULL | Bee           | NULL              |
+-------------+---------------+-------------------+
```
#### **14.3 RIGHT JOIN**
> RIGHT (OUTER) JOIN: Select records from the second (right-most) table with matching left table records.
```sql 
SELECT 
b.employee_id, 
a.name as employee_name, 
b.position as employee_position 
FROM employees a 
RIGHT JOIN employments b ON b.employee_id = a.id;

+-------------+---------------+-------------------+
| employee_id | employee_name | employee_position |
+-------------+---------------+-------------------+
|           1 | John          | IT Engineer       |
|           2 | Smith         | HR Manager        |
|           3 | Mark          | Admin Manager     |
|           4 | Dee           | PHP Developer     |
|           6 | Rose          | HR Officer        |
|           7 | Cherry        | Admin Officer     |
|           9 | NULL          | Web Developer     |
+-------------+---------------+-------------------+

```
#### **14.4 FULL JOIN**
> FULL (OUTER) JOIN: Selects all records that match either left or right table records.
```sql 
SELECT 
b.employee_id, 
a.name as employee_name, 
b.position as employee_position 
FROM employees a 
LEFT JOIN employments b ON b.employee_id = a.id
UNION ALL 
SELECT 
b.employee_id, 
a.name as employee_name, 
b.position as employee_position 
FROM employees a 
RIGHT JOIN employments b ON b.employee_id = a.id;

+-------------+---------------+-------------------+
| employee_id | employee_name | employee_position |
+-------------+---------------+-------------------+
|           1 | John          | IT Engineer       |
|           2 | Smith         | HR Manager        |
|           3 | Mark          | Admin Manager     |
|           4 | Dee           | PHP Developer     |
|           6 | Rose          | HR Officer        |
|           7 | Cherry        | Admin Officer     |
|        NULL | Bee           | NULL              |
|           1 | John          | IT Engineer       |
|           2 | Smith         | HR Manager        |
|           3 | Mark          | Admin Manager     |
|           4 | Dee           | PHP Developer     |
|           6 | Rose          | HR Officer        |
|           7 | Cherry        | Admin Officer     |
|           9 | NULL          | Web Developer     |
+-------------+---------------+-------------------+
```