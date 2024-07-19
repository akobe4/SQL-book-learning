## Chapter 4: Filtering 

#### Using Subqueries
Example: you can assume any film whose title has the string 'PET' is safe for family viewing, you could execute a query against the film table to retrieve all ratings associated with these films and then retrieve all films having any of these ratings 

```SQL 
SELECT title
	,rating
FROM film
WHERE rating IN (SELECT rating FROM film WHERE title LIKE '%PET%');
```

Results

![alt text](image.png)


#### Matching Conditions 
You can use a built in function to strip off the first letter of the last_name column to get all last names that begin with 'Q'

```SQL
SELECT last_name
	,first_name
FROM customer 
WHERE left(last_name, 1) = 'Q';
```

Results

![alt text](image-1.png)


Using Wildcards 

```SQL
SELECT last_name
	,first_name
FROM customer
WHERE last_name LIKE 'Q%' OR last_name LIKE 'Y%';
```

Results


![alt text](image-2.png)


To test whether an expression is NULL you need to use the 'IS NULL' operator 

```SQL
SELECT rental_id
	,customer_id
FROM rental
WHERE return_date IS NULL;
```

Results 

![alt text](image-3.png)


If you want to see whether a value has been assigned to a column you can use the 'IS NOT NULL' operator 

```SQL
SELECT rental_id
	,customer_id
	,return_date
FROM rental
WHERE return_date IS NOT NULL;
```

Result


![alt text](image-4.png)


#### Exercises 
**Exercise 4-1**
Which of the payment ID's would be returned by the following conditions?
```SQL
customer_id <> 5 AND (amount >8 OR DATE(payment_date) = '2005-08-23')
```

Answer 
101, 107

**Exercise 4-2**
Which of the payment ID's would be returned by the following filter conditions?
```SQL
customer_id = 5 AND NOT (amount > 6 OR date(payment_date) = '2005-06-19')
```

Answer
108, 110, 111, 112, 113, 115, 116, 117, 118, 119, 120

**Exercise 4-3**
Construct a query that retrieves all rows from the payments table where the amount is either 1.98, 7.98 or 9.98.

```SQL
mysql> SELECT *
    -> FROM payment
    -> WHERE amount IN (1.98, 7.98, 9.98);
```

![alt text](image-5.png)


postgres 
```SQL
SELECT *
FROM payment 
WHERE amount IN ('1.98', '7.98', '9.98');
```

![alt text](image-6.png)


**Exercise 4-4**
Construct a query that finds all customers whose last name contains an A in the second position and a W anywhere after the A

```SQL
SELECT * 
FROM customer
WHERE last_name LIKE '_A%W%';
```

![alt text](image-8.png)
