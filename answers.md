## Example:
1.
 - `SQL:`
    SELECT count(\*) from items

 - `ANSWER:`
   100

---

1.
 - `SQL:`
    select count(*) from users
 - `ANSWER:`
 +---------+
 |   count |
 |---------|
 |      50 |
 +---------+

2.
 - `SQL:`
    select items, title, price from items order by "price" DESC limit 5;
 - `ANSWER:`
 +---------------------------------------------------------------------------------------------------+-----------------------+---------+
 | items                                                                                             | title                 |   price |
 |---------------------------------------------------------------------------------------------------+-----------------------+---------|
 | (25,"Small Cotton Gloves","Automotive, Shoes & Beauty","Multi-layered modular service-desk",9984) | Small Cotton Gloves   |    9984 |
 | (83,"Small Wooden Computer",Health,"Re-engineered fault-tolerant adapter",9859)                   | Small Wooden Computer |    9859 |
 | (100,"Awesome Granite Pants",Toys,"Upgradable 24/7 access",9790)                                  | Awesome Granite Pants |    9790 |
 | (40,"Sleek Wooden Hat","Music & Baby","Quality-focused heuristic info-mediaries",9390)            | Sleek Wooden Hat      |    9390 |
 | (60,"Ergonomic Steel Car",Outdoors,"Enterprise-wide secondary firmware",9341)                     | Ergonomic Steel Car   |    9341 |
 +---------------------------------------------------------------------------------------------------+-----------------------+---------+

3.
  - `SQL:`
    select items, title, price from items order by "price" limit 1;
  - `ANSWER:`
  +-----------------------------------------------------------------------------------------------------+---------------------------+---------+
  | items                                                                                               | title                     |   price |
  |-----------------------------------------------------------------------------------------------------+---------------------------+---------|
  | (63,"Incredible Concrete Chair","Shoes, Toys & Music","Object-based even-keeled orchestration",121) | Incredible Concrete Chair |     121 |
  +-----------------------------------------------------------------------------------------------------+---------------------------+---------+
4.
  - `SQL:`
  select users.first_name, last_name from users, addresses where addresses.city = 'Willmouth' and street = '6439 Zetta Hills' and state =
........................... 'WY' and users.id = addresses.user_id
  - `ANSWER:`
+--------------+-------------+
| first_name   | last_name   |
|--------------+-------------|
| Corrine      | Little      |
+--------------+-------------+

5.
  - `SQL:`
    select users.id from users, addresses where users.first_name = 'Virginie' and last_name = 'Mitchell' and users.id = addresses.user_id

    update addresses SET city = 'New York', state = 'NY', zip = '10108'  where user_id = 39
  - `ANSWER:`
  +------+
  |   id |
  |------|
  |   39 |
  +------+

  +------+--------------+-------------+-----------------------------------+------+-----------+---------------------+----------+---------+-------+
  |   id | first_name   | last_name   | email                             |   id |   user_id | street              | city     | state   |   zip |
  |------+--------------+-------------+-----------------------------------+------+-----------+---------------------+----------+---------+-------|
  |   39 | Virginie     | Mitchell    | daisy.crist@altenwerthmonahan.biz |   41 |        39 | 12263 Jake Crossing | New York | NY      | 10108 |
  +------+--------------+-------------+-----------------------------------+------+-----------+---------------------+----------+---------+-------+
6.
 - `SQL:`
    select sum(price) from items
 - `ANSWER:`

 +--------+
 |    sum |
 |--------|
 | 467488 |
 +--------+
7.
- `SQL:`
select sum(quantity) from orders
- `ANSWER:`
+-------+
|   sum |
|-------|
|  2125 |
+-------+
8.
 - `SQL:`
select sum(orders.quantity * items.price)  from orders, items where orders.item_id = items.id and items.category = 'Books'
 - `ANSWER:`
 +--------+
 |    sum |
 |--------|
 | 420566 |
 +--------+
9.
- `SQL:`
INSERT INTO users(id,first_name,last_name,email) VALUES(51,'Jose','Campos','jjoseccampos@gmail.com');

INSERT INTO orders(id,user_id,item_id,quantity,created_at) VALUES(377,51,91,4,'2015-02-09 00:40:31.307444');
- `ANSWER:`
INSERT 0 1
Time: 0.039s

INSERT 0 1
Time: 0.007s
