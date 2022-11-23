# 1. Data exploration
## 2. Exploratory analysis of rental table

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


|
|     
|    
|     
