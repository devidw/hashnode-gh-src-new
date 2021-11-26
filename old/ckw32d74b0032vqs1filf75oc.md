## A practical example of normalization in relational databases

After learning about the concept of [primary keys](https://xn--david-9u04d.to/introduction-into-primary-keys-in-relational-databases) as well as [foreign keys](https://xn--david-9u04d.to/introduction-into-foreign-keys-in-relational-databases) in relation databases and how to use them in theory, its time to take that onto a more practical level. 

In this article, we will cover a practical example of how to apply the  [rules of database normalization](https://en.wikipedia.org/wiki/Database_normalization)  to a given database table, which is **not** normalized.

Here is our example table to start with:

<table border="1" style="width:250px;"><tbody><tr><td align="left" valign="top" width="12%">**KundenNr**</td><td align="left" valign="top" width="12%">**Name**</td><td align="left" valign="top" width="12%">**Vorname**</td><td align="left" valign="top" width="12%">**Betrieb**</td><td align="left" valign="top" width="12%">**Leitung**</td><td align="left" valign="top" width="12%">**ArtikelNr**</td><td align="left" valign="top" width="12%">**Art.beschreibung**</td><td align="left" valign="top" width="12%">**Auflage**</td></tr><tr><td align="left" valign="top" width="12%">1</td><td align="left" valign="top" width="12%">Jürgens</td><td align="left" valign="top" width="12%">Ina</td><td align="left" valign="top" width="12%">Maier AG</td><td align="left" valign="top" width="12%">Lempel</td><td align="left" valign="top" width="12%">2</td><td align="left" valign="top" width="12%">Flyer</td><td align="left" valign="top" width="12%">2000</td></tr><tr><td align="left" valign="top" width="12%">2</td><td align="left" valign="top" width="12%">Schmidt</td><td align="left" valign="top" width="12%">Tom</td><td align="left" valign="top" width="12%">Müller GmbH</td><td align="left" valign="top" width="12%">Breier</td><td align="left" valign="top" width="12%">3</td><td align="left" valign="top" width="12%">Karte</td><td align="left" valign="top" width="12%">5000</td></tr><tr><td align="left" valign="top" width="12%">3</td><td align="left" valign="top" width="12%">Jäger</td><td align="left" valign="top" width="12%">Franz</td><td align="left" valign="top" width="12%">Maier AG</td><td align="left" valign="top" width="12%">Lempel</td><td align="left" valign="top" width="12%">1, 2, 3</td><td>Karte, Flyer, Plakat</td><td align="left" valign="top" width="12%">1000, 500, 3000</td></tr><tr><td align="left" valign="top" width="12%">4</td><td align="left" valign="top" width="12%">Olsen</td><td align="left" valign="top" width="12%">Ina</td><td align="left" valign="top" width="12%">Schulze AG</td><td align="left" valign="top" width="12%">Sommer</td><td align="left" valign="top" width="12%">2</td><td align="left" valign="top" width="12%">Flyer</td><td align="left" valign="top" width="12%">500</td></tr><tr><td align="left" valign="top" width="12%">5</td><td align="left" valign="top" width="12%">Jürgens</td><td align="left" valign="top" width="12%">Paula</td><td align="left" valign="top" width="12%">Müller GmbH</td><td align="left" valign="top" width="12%">Breier</td><td align="left" valign="top" width="12%">1</td><td>Karte</td><td align="left" valign="top" width="12%">3000</td></tr></tbody></table>

Our goal is it to bring that table into the third form of normalization. 

Let's go ahead and get the job done.

Here is our `customers` table:

| id | last_name | first_name | company_id
| - | - | - | -
| 1 | Jürgens | Ina | 1
| 2 | Schmidt | Tom | 2
| 3 | Jäger | Franz | 1
| 4 | Olsen | Ina | 3
| 5 | Jürgens | Paula | 2

And our companies `ceos`s table:

| id | last_name
| - | -
| 1 | Lempel
| 2 | Breier
| 3 | Sommer

`companies` table goes here:

| id | name | ceo_id
| - | - | -
| 1 | Maier AG | 1
| 2 | Müller GmbH | 2
| 3 | Schulze AG | 3

Here is our `products` table:

| id | name
| - | -
| 1 | Karte
| 2 | Flyer
| 3 | Plakat

And the `orders`:

| id | customer_id
| - | -
| 1 | 1
| 2 | 2
| 3 | 3
| 4 | 4
| 5 | 5

Here we go for our `order_items`:

| id | order_id | product_id | product_amount
| - | - | - | -
| 1 | 1 | 2 | 2000
| 2 | 2 | 3 | 5000
| 3 | 3 | 1 | 1000
| 4 | 3 | 2 | 500
| 5 | 3 | 3 | 3000
| 6 | 4 | 2 | 500
| 7 | 5 | 1 | 3000

## Conclusion
Feel free to play around with the original table and add data to get into the game of optimizing the way data is designed through different tables using primary and foreign keys.