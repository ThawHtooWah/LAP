### VIEWS
> A database view is a searchable object in a database that is defined by a query.    
> Refers to a views as **virtual tables** 

#### 16.1 Create View
```sql
CREATE VIEW view_name AS query; 
```
> Assume as creating a view of IT employee list.
```sql
CREATE VIEW it_employees AS
SELECT * FROM employees a 
INNER JOIN employments b ON b.employee_id = a.id 
WHERE b.department = 'IT';

mysql> SELECT * FROM it_employees;
+----+------+------------+-------------+------------+---------------+-------------+-------------+
| id | name | address    | employee_id | department | position      | salary      | joined_date |
+----+------+------------+-------------+------------+---------------+-------------+-------------+
|  1 | John | Insein     |           1 | IT         | IT Engineer   | 100000.5000 | 2012-01-01  |
|  4 | Dee  | Botahtaung |           4 | IT         | PHP Developer | 200000.0000 | 2016-12-01  |
|  8 | Bee  | Insein     |           8 | IT         | Web           | 100000.0000 | 2022-01-01  |
+----+------+------------+-------------+------------+---------------+-------------+-------------+
3 rows in set (0.00 sec)

```