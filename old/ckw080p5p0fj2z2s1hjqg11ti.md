## Introduction into primary keys in relational databases

You just learned about the core concept of relational databases and how they are built up in databases, tables, rows, and columns? And now you want to take it further — good decision. In this article, we will speak about an important concept in the design of relational databases: keys.

## Introduction

So let's keep on that track of gaining new knowledge and directly dive into the important role of keys in databases.

Fundamentally, there are a bunch of different keys available for usage in databases. For the scope of this article, we will mainly focus on the most significant key database design: the _primary key_.

Imagine you are working on a web application, and it's your job to create the database tables for this application. Let's say you have created the following table to store the users' data, including their `name` and their `password`.

| name | password
| - | -
| Alisa | 3z]Eu&n_
| John | n+xL6h<f
| Jane | 37?,wW;u
| John | @'bYVP5"

Beside the fact that passwords should **never ever** be stored in plain text, rather they have to be stored as hashes, there is another problem in that table.

Imagine some registered users wants to delete his/her account in your application.

To perform a delete operation, we have to tell the database server which record we want to delete.

So let's say `Alisa` wants to delete her account. Here is what happens:

1. She passes her name to the application,
2. the application turns that into a format our database server understands and sends it to the server, 
3. the server executes the incoming query and the user with the `name` of `Alisa` gets removed from the system.

After the deletion, our database table will look like the following:

| name | password
| - | -
| John | n+xL6h<f
| Jane | 37?,wW;u
| John | @'bYVP5"

Now let's say `John` wants to delete his account, too. 

Beside the fact that we are building a bad web application, when 2 of 4 of our users are deleting their accounts 😄, here is when the previously mentioned problems comes into game.

There are two records and both of them have a `name` of `John`, but we only have the `name` of `John`, nothing more to identify him.

So, what would happen here, when `John` triggers that delete button, is that his account can not be deleted in a way it should.

That's so because there is no way for the system to know which of those users accounts wants to have his account deleted: is it `John` or is it`John`?

In the worst-case scenario, both `John`s would get deleted.

You get the problem.

So, now, what to do?

### Primary keys
The solution for that problem is to give the database table a column with a unique key, which will automatically be generated and also incremented each time we store a new record in our table. This type of key is a called a _primary key_.

In other words: keys are a way to store each row in a table as a unique row.

| id | name | password
| - | - | -
| 1 | Alisa | 3z]Eu&n_
| 2 | John | n+xL6h<f
| 3 | Jane | 37?,wW;u
| 4 | John | @'bYVP5"

Looking back at our `John`s, when we have a column with a key, an identification column, commonly named as `id`. We can now easily make sure we get the right record by using its unique identification stored in the `id`-column to perform any type of operation on that user.

## Conclusion
Problem solved. Knowledge gained!

Congratulations, you have just earned the _primary key_ to your magic keychain of database development. Use it wisely.