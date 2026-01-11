# Домашнее задание к занятию "`Защита сети`" - `Уляшев Дмитрий`



### Задание 1

Логи Suricata:
![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/11.jpg)

Suricata по разному отреагировал на каждый запущенный тест, какие-то более скрытные тесты были помечены как подозрительная активность, а открытое SYN тестирование была помечена как атака.
Fail2Ban никак не отреагировал на тесты.


### Задание 2

Логи Suricata:
![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/21.jpg)

Логи Fail2Ban:
![alt text](https://github.com/slav1power/sys-pattern-homework/blob/main/img/22.jpg)

Suricata обозначил подбор пароля как попытку кражи данных.
Fail2Ban обнаружив подбор, забанил атакующий ip







