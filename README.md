# Домашнее задание к занятию "`Работа с данными (DDL/DML)`" - `Уляшев Дмитрий`



### Задание 1

Репликация master-slave:
Это наиболее распространённая схема, в которой есть один главный сервер и один или несколько подчинённых.
В этой конфигурации:

 Master (ведущий) — основной сервер. Все операции записи (INSERT,
UPDATE, DELETE) происходят только на нём.

 Slave (ведомый) — копия мастера. Он получает все изменения от
мастера и обслуживает запросы на чтение (SELECT).

Репликация master-master:

В этой конфигурации все серверы равноправны — каждый является одновременно и мастером, и слейвом для другого. Запросы на запись или чтение можно отправлять на любой из серверов, и изменения будут распространены на все остальные. Такая схема повышает отказоустойчивость: если один из мастеров выйдет из строя, система продолжит работу, используя оставшиеся серверы.


### Задание 2

slave конфиг
```
[mysqld]
server-id = 2
read-only = 1
```

master конфиг
```
[mysqld]
server-id = 1
log-bin = mysql-bin
binlog-format = ROW
```

Привязка slave к master
```
CHANGE MASTER TO
 MASTER_HOST='mysql-master',
 MASTER_USER='repl',
 MASTER_PASSWORD='slavepass',
 MASTER_LOG_FILE='mysql-bin.000004',
 MASTER_LOG_POS=157;
```

Статус ведомой БД с таблицей созданной на мастере

![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/slave.jpg)


Статус ведущей Мастер БД

![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/master.jpg)






