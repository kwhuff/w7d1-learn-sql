1. 50

select max(id) as total from users;
--------------------------------------------------------------------------------
2. Small Cotton Gloves (9,984), Small Wooden Computer (9,859), Awesome Granite Pants (9,790), Sleek Wooden Hat (9,390), Ergonomic Steel Car (9,341)

select * from items order by price desc;
--------------------------------------------------------------------------------
3.  Ergonomic Granite Chair is cheapest item with category "Books" (1496).  Ergonomic Granite Chair is also the cheapest item with category that contains "Books", though the search produces 6 more results.

select * from items where category='Books' order by price;
select * from items where category like '%Books%' order by price;
--------------------------------------------------------------------------------
4.  Corrine Little, also has address:  54369 Wolff Forges Lake Byron CA 31587

select * from users inner join addresses where users.id=addresses.user_id;
--------------------------------------------------------------------------------
5.  
select * from users order by last_name;
select * from addresses where user_id=39;
update addresses set city='New York', zip="10108" where id=41;
--------------------------------------------------------------------------------
6.  All items with category = 'Tools' would cost 7,383.
All items with category containing ='Tools' would cost 46,477.

select sum(price) from items where category='Tools'; (7,383)
select sum(price) as total from items where category like '%Tools%'; (46,477)
--------------------------------------------------------------------------------
7.  2,125

select sum(quantity) as total from orders;
--------------------------------------------------------------------------------
8.  1,081,352

select items.category, sum(orders.quantity*items.price) "sum of price" from orders INNER JOIN items on orders.item_id=items.id where items.category like '%Books%';
--------------------------------------------------------------------------------
9.  insert into users (first_name, last_name, email) values ('Kyle', 'Huff', 'kwhuff@gmail.com');

insert into orders (user_id, item_id, quantity, created_at) values ('51', '40', '76', datetime(3));
