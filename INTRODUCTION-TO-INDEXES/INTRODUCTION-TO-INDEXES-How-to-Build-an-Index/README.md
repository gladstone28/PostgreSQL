


### INTRODUCTION TO INDEXES

## How to Build an Index

Now that we have talked about what an index is for, let us now build one ourselves.

In PostgreSQL, the CREATE INDEX keywords can be used to create an index on a column of a table. Say you wanted to create an index called customers_user_name_idx on the customers table on the user_name column, this is how you would do that:
```
CREATE INDEX customers_user_name_idx ON customers (user_name);
```
Keep in mind that indexes are great for searching but like everything in life, nothing comes without a cost. In the case of indexes, it comes at the cost of increased runtime for any modification to the table data impacting the user_name column. Another cost is the space that the index takes up. We will go into more detail on these issues later.


### Instructions
Checkpoint 1 Passed
1. Create an index called customers_city_idx on the customers table for the city column.

If you would like to confirm your index was successfully built you can check the table to see, recall this is done by running:
```
SELECT *
FROM pg_Indexes
WHERE tablename = 'customers';
```
change the example index name to customers_city_idx and change the column to city.

