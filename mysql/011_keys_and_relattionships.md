### KEYS AND RELATIONSHIPS
> Keys includes 
> - Primary Key
> - Unique Key
> - Index Key  
> 
> Relationships means the refreences between the tables


#### **11.1 Primay Key and Unique Key**
```sql
CREATE TABLE customers 
(
  id int,
  name varchar(100),
  nrc varchar(64),
  PRIMARY KEY(id),
  UNIQUE(nrc) 
);

DESC customers;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| id    | int          | NO   | PRI | NULL    |       |
| name  | varchar(100) | YES  |     | NULL    |       |
| nrc   | varchar(64)  | YES  | UNI | NULL    |       |
+-------+--------------+------+-----+---------+-------+
```

#### **11.2 Index Key and Relationships**
```sql
CREATE TABLE transactions
(
  id int,
  customer_id int,
  amount decimal,
  category varchar(64),
  notes text,
  PRIMARY KEY(id),
  INDEX(customer_id),
  INDEX(category),
  FOREIGN KEY(customer_id) REFERENCES customers(id) 
);

DESC transactions;
+-------------+---------------+------+-----+---------+-------+
| Field       | Type          | Null | Key | Default | Extra |
+-------------+---------------+------+-----+---------+-------+
| id          | int           | NO   | PRI | NULL    |       |
| customer_id | int           | YES  | MUL | NULL    |       |
| amount      | decimal(10,0) | YES  |     | NULL    |       |
| category    | varchar(64)   | YES  | MUL | NULL    |       |
| notes       | text          | YES  |     | NULL    |       |
+-------------+---------------+------+-----+---------+-------+

```
