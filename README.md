# Домашнее задание к занятию "`Работа с данными (DDL/DML)`" - `Уляшев Дмитрий`



### Задание 1

1.3     ![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/1.jpg)


1.5     ![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/2.jpg)


1.8     ![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/3.jpg)

```
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'logpass';
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost';
FLUSH PRIVILEGES;
SELECT user, host FROM mysql.user;
SHOW GRANTS FOR 'sys_temp'@'localhost';

docker exec -i mysql8 mysql -u root -prootpassword < sakila-schema.sql

docker exec -i mysql8 mysql -u root -prootpassword < sakila-data.sql

SHOW DATABASES;
USE sakila;
SHOW TABLES;
```


### Задание 2

```
Название таблицы | Название первичного ключа
actor            | actor_id
address          | address_id
category         | category_id
city             | city_id
country          | country_id
customer         | customer_id
film             | film_id
film_actor       | actor_id, film_id
film_category    | film_id, category_id
film_text        | film_id
inventory        | inventory_id
language         | language_id
payment          | payment_id
rental           | rental_id
staff            | staff_id
store            | store_id
```







