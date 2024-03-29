# Домашнее задание к занятию "`Работа с данными (DDL/DML)`" - `Яковлев Константин`

### Задание 1

```
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp.

1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)

1.4. Дайте все права для пользователя sys_temp.

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)

1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:
```
```
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
```
1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.

1.7. Восстановите дамп в базу данных.

1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.
```

![job1.3](https://github.com/Prime2270/homework_netology-12-02/blob/main/screenshots/job1.3.png)

![job1.5](https://github.com/Prime2270/homework_netology-12-02/blob/main/screenshots/job1.5.png)

![job1.8](https://github.com/Prime2270/homework_netology-12-02/blob/main/screenshots/job1.8.png)

```
авторизация в mysql
mysql -h 127.0.0.1 -P 3306 -u root -p
ввод пароля
создание пользователя 
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY '12345';
получение списка всех пользователей
SELECT user FROM mysql.user;
назначение всех привелегий
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost';
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%';
активация изминений
FLUSH PRIVILEGES;
повторная авторизация в mysql
mysql -h 127.0.0.1 -P 3306 -u sys_temp -p
ввод пароля
SHOW DATABASES;
вывод списка бд
CREATE DATABASE sakila;
создание бд в которую будет загружен дамп
mysql -h 127.0.0.1 -P 3306 -u sys_temp -p sakila < /home/prime/docker_homework/sakila-db/sakila-data.sql
mysql -h 127.0.0.1 -P 3306 -u sys_temp -p sakila_schema_db < /home/prime/docker_homework/sakila-db/sakila-schema.sql
начало работы в бд
USE sakila;
вывод списка таблиц в бд
SHOW tables;
просмотр содержимого столбца
SHOW COLUMNS FROM <имя столбца>;
```
### Задание 2

```
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: 
в первом должны быть названия таблиц восстановленной базы, 
во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)
```
```
Название таблицы | Название первичного ключа
customer         | customer_id
```
![job2](https://github.com/Prime2270/homework_netology-12-02/blob/main/screenshots/job2.png)
