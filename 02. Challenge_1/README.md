Here we are going to explore some challenges, starting from the easiest to the tougher ones

## Q1. How many payment transactions were greater than $5.00?

```
SELECT COUNT(amount) FROM payment
WHERE amount > 5;
```

*Output:*

|count|
|----:|
|3618 |


## Q2. How many actors have a first name that starts with the letter P?

```
SELECT COUNT(*) FROM actor
WHERE first_name LIKE 'P%';
```

## Q3. How many unique districts are our customers from?

```
SELECT COUNT(DISTINCT(district)) 
FROM address;
```

## Q4. Retrieve the list of names for those distinct districts from the previous question.

```
SELECT DISTINCT(district) FROM address;
```

## Q5. How many films have a rating of R and a replacement cost between $5 and $15?

```
SELECT COUNT(*) FROM film
WHERE rating = 'R'
AND replacement_cost BETWEEN 5 AND 15;
```

## Q6. How many films have the word Truman somewhere in the title?

```
SELECT COUNT(*) FROM film
WHERE title LIKE '%Truman%';
```





