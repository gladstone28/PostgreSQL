link to lesson:

https://www.codecademy.com/paths/design-databases-with-postgresql/tracks/how-do-i-make-sure-my-database-stays-fast/modules/indexes/lessons/indexes-part-1/exercises/impact-of-indexes



### INTRODUCTION TO INDEXES

## Impact of Indexes

Let’s do some experimenting now to see the power of indexes in practice. We will cover the cost of indexes later on, for now, let’s just focus on the positive aspects of them: filtering data.

As a note, this page will most likely run slower for you than any other exercise in this lesson. In order to see the benefits of an index, you need a large database. It may take some time to load the database and run your code. In future exercises, we will be working with smaller databases to not slow down your experience, but it’s important for you to see the impact indexes can have, so please have patience with this exercise.

To get insight into how PostgreSQL breaks down your statements into runnable parts, we can investigate the query plan by adding EXPLAIN ANALYZE before your query. Rather than returning the results of the query, it will return information about the query.


```
EXPLAIN ANALYZE SELECT *
FROM customers;

```
This would return the plan that the server will use to give you every row from every record from the customers table.

There is a good amount of information on what you can get from this and a full understanding is outside the scope of this lesson. If you would like to learn more, PostgreSQL’s official website has a full explanation of EXPLAIN.

For now, there are a few key things you should take note of. The first is the planner will specifically tell you how it is searching. If you see “Seq Scan” this means that the system is scanning every record to find the specific records you are looking for. If you see “Index” (in our examples more specifically “Bitmap Index Scan”) you know that the server is taking advantage of an index to improve the speed of your search.

The other part to take note of is the “Planning time” and “Execution time”. The planning time is the amount of time the server spends deciding the best way to solve your query, should it use an index, or do a full scan of the table(s) for instance. The execution time is the amount of time the actual query takes to run after the server has decided on a plan of attack. You need to take both of these into consideration, and when examining your own indexes these are critical to understanding how effective your indexes are.

### Instructions

Let’s start with a search on a column without an index. Select all columns from the rows of the customers table where first_name is 'David'. Before running your query, add EXPLAIN ANALYZE to the start of it.

Your query should look like:
Hint
```
EXPLAIN ANALYZE SELECT *
FROM <table_name>
WHERE <column_name> = <equality_check>;
```

in this case

- <table_name> = customers
- <column_name> = first_name
- <equality_check> = 'David' (note the quotes and capitalization)
