## Introduction into foreign keys in relational databases

Let's take your journey on database development one step further and learn about another important type of key: _foreign keys_.

To get the idea behind foreign keys, let's imagine the practical usage of databases in an online shop application.

In an online shop there is a lot of different data which all as to be stored in the database. And it also has to be linked together correctly to make sure we don't have any redundant data in our databases.

Redundant data is when the same data is stored multiple times. And we really **don't** want to have such data duplicates in our database.

Redundant data is pain because:

* It increases the amount of space our database will need, which means we have to pay for more space, while we don't store more information in the database. Because we store the information twice or even hundreds or thousands of times.
* It also slows down our database server for no reason.
* Furthermore, the database gets really hard to maintain. And it generally gets really hard to work with the database, because we have to make sure that on any operation on these duplicated data is executed on all duplicates.
* So, it slows down our own application beside the database server as well.

Back to our web store. What kinds of data do we have to expect, we have to save in the database?

Here are a few, so you get an idea about what we have to deal with:

* Customers
* Products
* Orders

So, since we hate redundant data, it totally makes sense to create individual tables for those entities in our database.

But wait, how do we actually link those tables between each other, to make things work?

Well, that's when _foreign keys_ come into play.

To prepare our tables to work with foreign keys, we will add a _primary key_ to each of those tables and name the column `id`.

Here we go for our `customers` table:

| id | first_name | last_name | email | phone | password
| - | - | - | - | - | -
| 1 | John | Doe | john@d.oe| 2025550191 | d1e8a70b5ccab1dc2f56bbf7e99f064a660c08e361a35751b9c483c88943d082

And our `products` table:

| id | title | description | price | stock
| - | - | - | - | - | 
| 1 | Pizza | So tasty | 5,00 | 3

Next up, there's our `orders` table. 

Now, things are getting more interesting, we will create our first foreign key: `customer_id`.

| id | date | customer_id |
| - | - | -
| 1 | 1970-01-01 | 1

Here, we linked the buyers to their orders using the `customer_id` column in the `orders` table, which references the primary key inside the `id` column of the `customers` table.

You noticed there is something missing in the `orders` table? 

Yes, absolutely, there is no information of what the customer actually bought. We are only storing the `date`, but nothing what says us, what we have to ship, which is kind of fundamental, isn't it? 😄

We could have added a `items` column to the `orders` table. **BUT**, doing so would have resulted in table cells storing multiple information in one single cell (for example, a comma separated list of `product_id`s).

And that's definitely nothing we want, things would get kind of ugly, as we can't work cleanly with these cell contents. Because each time we need the individual products, we would have to integrate our own logic in our application, to separate this single cells into separate products again.

So to fix that we need one last table, which stores all individual items, which were ordered together in one order. We name it the `order_items` table. 

The process to split up multiple pieces of data stored in only one single column to multiple columns/tables with one information per column is called *atomization*.

| id | order_id | product_id
| - | - | -
| 1 | 1 | 1

Using foreign keys to reduce **redundant** data and also for **atomization**, we were able to separated all the stored data nicely into individual tables. Also, we made sure there is only one piece of data per cell — we don't have to care about data duplicates anymore.

And that's pretty much it for that practical example of an online shop.

## Conclusion
Yeah, you just unlocked the _foreign key_ on your magical keychain of database development. Use it wisely.