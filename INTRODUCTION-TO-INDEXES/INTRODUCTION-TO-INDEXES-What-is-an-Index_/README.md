link to lesson
https://www.codecademy.com/paths/design-databases-with-postgresql/tracks/how-do-i-make-sure-my-database-stays-fast/modules/indexes/lessons/indexes-part-1/exercises/what-is-an-index

INTRODUCTION TO INDEXES
What is an Index?
7 min
When working with databases on Codecademy, many lessons use relatively small databases. However, when working with databases in practice, they can become massive very quickly. Imagine, for instance, if you had a database with all the purchases, sales, employees, shipping data, and so on for a large retailer like Target, Wal-Mart, or Amazon. Their databases must be massive! Without good organization, large databases like that can become nothing more than a pile of unusable information. Designing your database thoughtfully with multiple tables, keys, and relationships can help, but what if you want to search through this massive amount of data and find specific records? That is where indexing comes into play.

An index is an organization of the data in a table to help with performance when searching and filtering records. A table can have zero, one, or many indexes. There are some costs when using indexes, which we will cover later in this lesson.

Let’s start by learning how to see what indexes already exist on a table. Say you want to see what indexes exist on your products table you would run the following query:

SELECT *
FROM pg_Indexes
WHERE tablename = 'products';

pg_Indexes is a built-in view in PostgreSQL. Different database servers have different ways to see their indexes.

During this lesson, we will be working mostly with a table customers created with randomly generated information. Depending on the exercise, the number of records might change to help with run times, but the structure of the table will remain unchanged.

In this lesson you will learn about:

What an index is and how they function.
How to build an index.
How to drop an index.
Multicolumn indexes to expand the power of your indexes.
Some of the benefits and burdens of indexes.
