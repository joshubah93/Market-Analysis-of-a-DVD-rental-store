In the previous challenge questions, we explored how to implement ```SELECT``` ,  ```SELECT DISTINCT``` , ```COUNT``` , ```ORDER BY``` , ```LIMIT``` ,  ```LIKE``` 
statements. In addition to that, we will go a step futher to explore the use of aggregate statements such ```GROUP BY``` , ```HAVING```  and  ```JOIN``` statement to solve real world scenario challenges.

## Q1. A customer forgot their wallet at our store! We need to track down their email to inform them. What is the email for the customer with the name Nancy Thomas?

```sql
SELECT email FROM customer
WHERE first_name = 'Nancy'
AND last_name = 'Thomas';
```

*Output:*
|email|
|:---:|
|nancy.thomas@sakilacustomer.org|


## Q2. A customer wants to know what the movie "Outlaw Hanky" is about. Could you give them the description for the movie "Outlaw Hanky"?

```sql
SELECT description FROM film
WHERE title = 'Outlaw Hanky';
```

*Output:*

|description|
|:---:|
|A Thoughtful Story of a Astronaut And a Composer who must Conquer a Dog in The Sahara Desert|

## Q3. We want to reward our first 10 paying customers. What are the customer ids of the first 10 customers who created a payment?

```sql
SELECT customer_id FROM payment
ORDER BY payment_date ASC;
LIMIT 10;
```

*Output:*

|customer_id|
|:---:|
|416|
|516|
|239|
|592|
|49|
|264|
|46|
|481|
|139|
|595|

## Q4. A customer wants to quickly rent a video to watch over their short lunch break. What are the titles of the 5 shortest (in length of runtime) movies?

```sql
SELECT title, length FROM film
ORDER BY length ASC
LIMIT 5;
```
|title	|length|
|:-----------------------:|:-----------:|
|Labyrinth League|	46|
|Alien Center|	46|
|Iron Moon|	46|
|Kwai Homeward|	46|
|Ridgemont Submarine| 46|


## Q5. If the previous customer can watch any movie that is 50 minutes or less in run time, how many options does she have?

```sql
SELECT COUNT(title) FROM film
WHERE length <= 50
```
*Output:*

|Count|
|:-------:|
|37|

## Q6. Corporate HQ is conducting a study on the relationship between replacement cost and a movie MPAA rating (e.g. G, PG, R,etc...).
### What is the average replacement cost per MPAA rating?
> Note: You may need to expand the AVG column to view correct results

```sql
SELECT rating, AVG(replacement_cost)
FROM film
GROUP BY rating
```
*Output:*

|rating| avg |
|:--------------:|:--------------------:|
|R|	20.2310256410256410|
|NC-17|	20.1376190476190476|
|G|	20.1248314606741573|
|PG|	18.9590721649484536|
|PG-13|	20.4025560538116592|


## Q7. We are running a promotion to reward our top 5 customers with coupons. What are the customer ids of the top 5 customers by total spend?

```sql
SELECT customer_id, SUM(amount)
FROM payment
GROUP BY customer_id
ORDER BY SUM(amount) DESC
LIMIT 5;
```

*Output:*

|customer_id|	sum|
|:---------:|:---------------:|
|148|	211.55|
|526|	208.58|
|178|	194.61|
|137|	191.62|
|144|	189.60|
## Q8. We are launching a platinum service for our most loyal customers. We will assign platinum status to customers that have had 40 or more transaction payments. What customer_ids are eligible for platinum status?

```sql
Solution
SELECT customer_id, COUNT(*)
FROM payment
GROUP BY customer_id
HAVING COUNT(*) >= 40;
```

*Output:*

|customer_id| count|
|:-------:|:-------:|
|144|	40|
|526|	42|
|148|	45|


## Q9. What are the customer ids of customers who have spent more than $100 in payment transactions with our staff_id member 2?

```sql
SELECT customer_id, SUM(amount)
FROM payment
WHERE staff_id = 2
GROUP BY customer_id
HAVING SUM(amount) > 100
```

|customer_id| sum|
|:-------:|:-------:|
|187|	110.81|
|522|	102.80|
|526|	101.78|
|211|	108.77|
|148|	110.78|

## Q10. California sales tax laws have changed and we need to alert our customers to this through email. What are the emails of the customers who live in California?

```sql
SELECT district, email FROM address
INNER JOIN customer ON
address.address_id = customer.address_id
WHERE district = 'California'
```

|district|	email|
|:------------:|:------------------------------------------------------:|
|California|	patricia.johnson@sakilacustomer.org|
|California|	betty.white@sakilacustomer.org|
|California|	alice.stewart@sakilacustomer.org|
|California|	rosa.reynolds@sakilacustomer.org|
|California|	renee.lane@sakilacustomer.org|
|California|	kristin.johnston@sakilacustomer.org|
|California|	cassandra.walters@sakilacustomer.org|
|California|	jacob.lance@sakilacustomer.org|
|California|	rene.mcalister@sakilacustomer.org|


##  Q11. A customer walks in and is a huge fan of the actor "Nick Wahlberg" and wants to know which movies he is in. Get a list of all the movies "Nick Wahlberg" has been in.

```sql
SELECT title,first_name,last_name
FROM film_actor 
INNER JOIN actor ON
film_actor.actor_id = actor.actor_id
INNER JOIN film
ON film_actor.film_id = film.film_id
WHERE first_name = 'Nick'
AND last_name = 'Wahlberg'
LIMIT 10;
```

*Output:*

|title|	 first_name |	 last_name|
|:------------:|:-----------------:|:------------------------------------:|
|Adaptation Holes|	Nick|	Wahlberg|
|Apache Divine|	Nick|	Wahlberg|
|Baby Hall|	Nick|	Wahlberg|
|Bull Shawshank|	Nick|	Wahlberg|
|Chainsaw Uptown|	Nick|	Wahlberg|
|Chisum Behavior|	Nick|	Wahlberg|
|Destiny Saturday|	Nick|	Wahlberg|
|Dracula Crystal|	Nick|	Wahlberg|
|Fight Jawbreaker|	Nick|	Wahlberg|
|Flash Wars|	Nick|	Wahlberg|


