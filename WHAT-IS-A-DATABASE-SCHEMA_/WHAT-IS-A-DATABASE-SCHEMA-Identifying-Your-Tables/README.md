

WHAT IS A DATABASE SCHEMA?
Identifying Your Tables
7 min
In this exercise, we are going to delve into designing our own database schema. The purpose of our database is to enable an online bookstore to show its catalog of books to potential buyers and for a buyer to preview sample chapters for a selected book. Imagine you are book browsing on Amazon.com.

After gathering information for this database, we found that our database should have:

book information which includes title, isbn, number of pages, price, description, and publisher for an overview of the book
author information which includes author bio and contact
book chapter information which includes chapter number, chapter title and chapter content that is available for online previewing
As you can see, there is quite a lot of information to maintain in our database. The next step would be to organize the information in our database into tables.

Take a look at a sample row below if we decide to store all our information in a single table. For the sake of space, we made the chapter information very small and unrealistic. If you would like to make this image bigger, you can expand this panel, or find the image here.


![]()

From the information provided, does it make sense to organize our data in one table? Is the table easy to use as is? Does it have too many columns covering different topics?

What makes up the bulk of this table? You are correct if you guess it’s the chapter content. The chapter content is useful when a potential buyer wants to preview a book. But not all books make their content available to the public. In such a case, the chapter content columns will be empty. To make this table easier to use, storing the chapter content in its own table makes more logical sense. This would also make the current table more lightweight and manageable. Therefore, we should restructure this table so that chapter-related information resides in its own table.

Now we are left with a table containing just book and author information. What if we are interested in contacting an author without needing to know what books they write? Would it make sense to consult this table which always links a book to its author? Or would it make more sense to keep the author information separate as well? The answer is ‘yes’ to the latter question.

Let’s practice organizing information by identifying tables in the following exercises.


### Instructions

Checkpoint 1 Passed
1.This exercise contains a poorly written schema for a student profile database. Open script.sql and type a query to select the content in the table profile.

You should see results similar to this:
