# MySQL

![](../.gitbook/assets/big6%20%281%29.png)

## Calling Database

```sql
USE dataBaseName;
```

## SELECT

> **SELECT** - Identifies the **column\(s\)** you want your query to select for your results.

![](../.gitbook/assets/select%20%281%29.png)

```sql
# Syntax
SELECT columnName
```

```sql
# Examples

# Return one or more specific columns in results by naming them
# Seperate column names with a comma
SELECT
    customer_id,
    rental_date
FROM rental;
```

### SELECT DISTINCT

![](../.gitbook/assets/selectdistinct.png)

## FROM

![](../.gitbook/assets/from.png)

> Comes **after** **SELECT**.

```sql
# Syntax
SELECT columnName 
FROM tableName
```

```sql
# Examples of SELECT and FROM

# Selects ALL columns from the specified table
# Without using a WHERE clause will return the entire table (all columns, all rows)
SELECT * 
FROM tableName
```

> **TIP** - `SELECT * FROM tableName`is a great way to quickly see what data a table contains.

## WHERE

![](../.gitbook/assets/where.png)

```sql
# Syntax
SELECT columnName 
FROM tableName 
WHERE logicalCondition

# Example
SELECT
	customer_id,
    rental_id,
    amount,
    payment_date
FROM payment
WHERE amount = 0.99

# Example 2
SELECT
	customer_id,
    rental_id,
    amount,
    payment_date
FROM payment
WHERE payment_date > '2006-01-01'
```

> Comes **after** **FROM**.

### WHERE Operators

![](../.gitbook/assets/where%20%281%29.png)

### WHERE Examples

![](../.gitbook/assets/where2.png)

### WHERE & AND

![](../.gitbook/assets/whereandand.png)

### WHERE & OR

![](../.gitbook/assets/2019-07-17%20%281%29.png)

### WHERE & IN

![](../.gitbook/assets/2019-07-17%20%282%29.png)

### LIKE

![](../.gitbook/assets/2019-07-17_1.png)

### WILDCARD

![](../.gitbook/assets/2019-07-17_2.png)

## GROUP BY

![](../.gitbook/assets/2019-07-17_3.png)

```sql
# Syntax
SELECT columnName 
FROM tableName 
WHERE logicalCondition 
GROUP BY columnName
```

> Comes **after** **WHERE**.

## HAVING

> **HAVING** - _\(Optional\)_ Specifies group-filtering criteria for filtering specific groups based on certain criteria.   
>  Comes after **GROUP BY** and can only be used when **GROUP BY** is present.

```sql
# Syntax
SELECT columnName 
FROM tableName 
WHERE logicalCondition 
GROUP BY columnName 
HAVING logicalCondition
```

## ORDER BY

> **ORDER BY** - \(Optional\) Specifies the order \(sorting records\) in which your query results are displayed.   
> Comes **last** in query.

```sql
# Syntax
SELECT columnName 
FROM tableName 
WHERE logicalCondition 
GROUP BY columnName 
HAVING logicalCondition 
ORDER BY columnName
```

