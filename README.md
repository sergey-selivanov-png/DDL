# Домашнее задание к занятию 12.02 - "`Работа с данными (DDL/DML)`" - `Selivanov Sergey`

### Задание 1

![Скриншот-1](https://github.com/sergey-selivanov-png/DDL/blob/main/image/s1.png)

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

#### ОТВЕТ:
![Скриншот-2](https://github.com/sergey-selivanov-png/DDL/blob/main/image/s2.png)

1.6. Переподключитесь к базе данных от имени sys_temp.

#### ОТВЕТ:
![Скриншот-3](https://github.com/sergey-selivanov-png/DDL/blob/main/image/s3.png)

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

#### ОТВЕТ:
![Скриншот-4](https://github.com/sergey-selivanov-png/DDL/blob/main/image/s4.png)

#### ОТВЕТ (простыня со всеми запросами):
```bash
# apt update
# apt install mysql-server mysql-client
# mysqladmin password -u root -p
# mysql_secure_installation
# mysql -u root -p
mysql> CREATE USER 'sys_test'@'localhost' IDENTIFIED BY 'password';
mysql> SELECT user,authentication_string,plugin,host FROM mysql.user;
mysql> GRANT ALL PRIVILEGES ON *.* TO 'sys_test'@'localhost';
mysql> show grants for 'sys_test'@'localhost';
mysql> exit
# mysql -u sys_test -p
mysql> SELECT user();
mysql> exit
# wget https://downloads.mysql.com/docs/sakila-db.zip
# apt install unzip
# unzip sakila-db.zip
# mysql -u sys_test -p
mysql> CREATE DATABASE `sakila`;
mysql> SHOW DATABASES;
mysql> exit
# export DBNAME=sakila
# mysql -u sys_test -p ${DBNAME} < /root/sakila-db/sakila-schema.sql
# mysql -u sys_test -p ${DBNAME} < /root/sakila-db/sakila-data.sql
# mysql -u sys_test -p
mysql> SHOW DATABASES;
mysql> USE sakila;
mysql> SHOW TABLES;
```

---
### Задание 2

![Скриншот-5](https://github.com/sergey-selivanov-png/DDL/blob/main/image/s5.png)
```
Название таблицы             | Название первичного ключа
actor                        | actor_id
actor_info                   | 
address                      | address_id
category                     | category_id
city                         | city_id
country                      | country_id
customer                     | customer_id
customer_list                | 
film                         | film_id
film_actor                   | actor_id, film_id
film_category                | film_id, category_id
film_list                    | 
film_text                    | film_id
inventory                    | inventory_id
language                     | language_id
nicer_but_slower_film_list   | 
payment                      | payment_id
rental                       | rental_id
sales_by_film_category       | 
sales_by_store               | 
staff                        | staff_id
staff_list                   | 
store                        | store_id
```
