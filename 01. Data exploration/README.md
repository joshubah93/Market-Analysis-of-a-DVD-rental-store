# 1. Data exploration
## 1.1. Exploratory analysis of rental table

The first table in our database schema is the rental table. Let's take a look at all the columns in the table. We'll limit the output to 5 rows.

```
SELECT * 
FROM rental
LIMIT 5;
```


*Output:*


 |  rental_id  | 	   rental_date      | inventory_id  |	customer_id |      return_date	   | staff_id |     last_update     |
 |-------------|----------------------|---------------|-------------|---------------------|---------:|---------------------|
 |      2	     |  2005-05-24 22:54:33 |   	 1525	     |     459	    | 2005-05-28 19:40:33 | 	   1	   | 2006-02-16 02:30:53 |
 |      3	     |  2005-05-24 23:03:39 |	    1711	     |     408	    | 2005-06-01 22:12:39 |	    1	   | 2006-02-16 02:30:53 |
 |      4	     |  2005-05-24 23:04:41 |	    2452	     |     333	    | 2005-06-03 01:43:41 |	    2	   | 2006-02-16 02:30:53 |
 |      5	     |  2005-05-24 23:05:21 |	    2079	     |     222	    | 2005-06-02 04:33:21 |	    1	   | 2006-02-16 02:30:53 |
 |      6	     |  2005-05-24 23:08:07 |	    2792	     |     549	    | 2005-05-27 01:32:07 |	    1	   | 2006-02-16 02:30:53 |


To know the total number of rentals in this store

```
SELECT 
COUNT (*) 
FROM rental;
```
*Output:*

|count|
|----:|
|16044|

Let's take a look at all the records for one customer.

```
SELECT *
FROM rental
WHERE customer_id = 1
LIMIT 5;
```


|rental_id|rental_date	       |inventory_id|customer_id|return_date	       |staff_id|last_update        |
|---------|-------------------|------------|-----------|-------------------|-------:|-------------------|
|76	      |2005-05-25 11:30:37|3021	       |1	         |2005-06-03 12:00:37|2	      |2006-02-16 02:30:53|
|573	     |2005-05-28 10:35:23|4020	       |1	         |2005-06-03 06:32:23|1      	|2006-02-16 02:30:53|
|1185	    |2005-06-15 00:54:12|2785	       |1	         |2005-06-23 02:42:12|2      	|2006-02-16 02:30:53|
|1422	    |2005-06-15 18:02:53|1021	       |1	         |2005-06-19 15:54:53|2	      |2006-02-16 02:30:53|
|1476	    |2005-06-15 21:08:46|1407	       |1          |2005-06-25 02:26:46|1	      |2006-02-16 02:30:53|


## 1.2. Exploratory analysis of category table

```
SELECT *
FROM category
```

category_id 	 name          last_update
1	            Action  	     2006-02-15 09:46:27
2	            Animation 	   2006-02-15 09:46:27
3	            Children 	    2006-02-15 09:46:27
4	            Classics 	    2006-02-15 09:46:27
5	            Comedy	       2006-02-15 09:46:27
6	            Documentary 	 2006-02-15 09:46:27
7	            Drama	        2006-02-15 09:46:27
8	            Family 	      2006-02-15 09:46:27
9	            Foreign 	     2006-02-15 09:46:27
10	           Games 	       2006-02-15 09:46:27
11	           Horror 	      2006-02-15 09:46:27
12	           Music 	       2006-02-15 09:46:27
13	           New 	         2006-02-15 09:46:27
14	           Sci-Fi 	      2006-02-15 09:46:27
15	           Sports 	      2006-02-15 09:46:27
16	           Travel        2006-02-15 09:46:27


## 1.3. Exploratory analysis of film table

```
SELECT 
  title,
  release_year,
  language_id,
  rental_duration,
  rental_rate,
  rating,
  last_update
FROM film
LIMIT 10;
```

title	              release_year   rental_duration	   rental_rate  	rating 	 last_update
Chamber Italian	    2006	          7	                 4.99	         NC-17 	  2013-05-26 14:50:58.951
Grosse Wonderful	   2006	          5	                 4.99	         R        2013-05-26 14:50:58.951
Airport Pollock	    2006	          6	                 4.99	         R        2013-05-26 14:50:58.951
Bright Encounters	  2006	          4	                 4.99	         PG-13    2013-05-26 14:50:58.951
Academy Dinosaur 	  2006	          6	                 0.99	         PG       2013-05-26 14:50:58.951
Ace Goldfinger	     2006	          3	                 4.99	         G        2013-05-26 14:50:58.951
Adaptation Holes	   2006	          7	                 2.99	         NC-17    2013-05-26 14:50:58.951
Affair Prejudice	   2006	          5	                 2.99	         G        2013-05-26 14:50:58.951
African Egg	        2006	          6	                 2.99	         G        2013-05-26 14:50:58.951
Agent Truman	       2006	          3	                 2.99	         PG       2013-05-26 14:50:58.951


|     
|    
|     
