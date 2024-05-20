INTRODUCTION TO INDEXES
What is the benefit of an Index?
4 min
Indexing allows you to organize your database structure in such a way that it makes finding specific records much faster. By default it divides the possible matching records in half, then half, then half, and so on until the specific match you are searching for is found. This is known as a Binary Tree, or B-Tree.

Let’s consider an example to expand on this concept. Say you had a sales department where you ranked your clients from number 1 to 100 in order of loyalty. If you wanted to search the database for your most loyal client, who would have a loyalty score of 100, you would have to search every record (the highest loyalty score could be anywhere in the data set). If you created an index on loyality_score, you could now use the B-Tree structure to speed up that search. The search would divide all results in half, so in this case, the first check would be if the record you are searching for is greater than or less than 50.

If you are familiar with logarithms, the worst-case speed for a B-Tree to find a record is log2n, where without it you would have to check every record, so the read time would be n.

In small databases this is negligible, but as the datasets get larger this becomes more significant. To highlight this, let us say you were searching 1,000,000 records. Without an index on the column you were searching, you would need to look through all 1,000,000 records (assuming its a non-unique column). With a B-Tree index, in the worst case, you would have to search 20 comparisons (log2n).

Instructions
Take a look at the applet on this page. Try searching for a specific number. How many items does the search look at if you don’t use a binary tree? How many items does the search look at with the binary tree?

Community Forums
Still have questions? View this exercise's thread in the Codecademy Forums.
