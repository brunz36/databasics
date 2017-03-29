## Example:
1.
 - `SQL:`
    SELECT count(\*) from items

 - `ANSWER:`
   100

---

1.
 - `SQL:`
    SELECT "count"(*) FROM users

 - `ANSWER:`
    50

2.
 - `SQL:`
    SELECT title, price FROM items ORDER BY price DESC limit 5;

 - `ANSWER:`
     +-----------------------+---------+
    | title                 |   price |
    |-----------------------+---------|
    | Small Cotton Gloves   |    9984 |
    | Small Wooden Computer |    9859 |
    | Awesome Granite Pants |    9790 |
    | Sleek Wooden Hat      |    9390 |
    | Ergonomic Steel Car   |    9341 |
    +-----------------------+---------+

3.
 - `SQL:`
    SELECT title, category, price FROM items where category like 'Books' order by price limit 1;

 - `ANSWER:`
     +-------------------------+------------+---------+
    | title                   | category   |   price |
    |-------------------------+------------+---------|
    | Ergonomic Granite Chair | Books      |    1496 |
    +-------------------------+------------+---------+

4.
- `SQL:`
  SELECT first_name, last_name, street, city,state from users, addresses where street = '6439 Zetta Hills' and city = 'Willmouth' and state = 'WY' and users.id = addresses.user_id;

- `ANSWER:`
  +--------------+-------------+
  | first_name   | last_name   |
  |--------------+-------------|
  | Corrine      | Little      |
  +--------------+-------------+

5.
- `SQL:`
  UPDATE addresses SET city = 'New York', state = 'NY', zip = '10108' FROM users WHERE first_name = 'Virginie' and last_name = 'Mitchell' and users.id = addresses.user_id;

- `ANSWER:`
  UPDATE 1
  -->>>> TO CHECK IT
  SELECT first_name, last_name, addresses.street, addresses.city, addresses.state, addresses.zip from users, addresses where first_name = 'Virginie' and city = 'New York' and state = 'NY' and users.id = addresses.user_id;
  +--------------+-------------+---------------------+----------+---------+-------+
  | first_name   | last_name   | street              | city     | state   |   zip |
  |--------------+-------------+---------------------+----------+---------+-------|
  | Virginie     | Mitchell    | 12263 Jake Crossing | New York | NY      | 10108 |
  +--------------+-------------+---------------------+----------+---------+-------+
SELECT 1

6.
- `SQL:`
  SELECT sum(price) from items where category = 'Tools'
-
  `ANSWER:`
  +-------+
  |   sum |
  |-------|
  |  7383 |
  +-------+

7.
- `SQL:`
  SELECT sum(quantity) from orders

- `ANSWER:`
  +-------+
  |   sum |
  |-------|
  |  2125 |
  +-------+

8.
- `SQL:`
  SELECT sum(quantity * price) from orders, items where orders.item_id = items.id and category = 'Books'

- `ANSWER:`
  +--------+
  |    sum |
  |--------|
  | 420566 |
  +--------+

9.
- `SQL:`
  INSERT INTO users(first_name, last_name, email) VALUES('Bruno', 'Ribeiro', 'brunz36@gmail.com'); INSERT INTO addresses(user_id, street, city, state, zip) VALUES ('1', '1108 Thornwood Dr.', 'Oldsmar', 'FL', '34677'); INSERT INTO orders(user_id, item_id, quantity, created_at) VALUES ('1', '36', '2', '2017-02-09 00:40:30.542598');

- `ANSWER:`
  INSERT 0 1
  INSERT 0 1
  INSERT 0 1
