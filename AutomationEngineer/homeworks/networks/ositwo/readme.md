[Текст задания](https://github.com/netology-code/pnet-homeworks/tree/main/2)
 
Основные шаги:
Создание Access Control List с правилами:
Разрешить трафик из VLAN 10 (192.168.10.0/24).
Заблокировать трафик из VLAN 20 (192.168.20.0/24).
Разрешить весь остальной трафик.
Применение ACL к интерфейсу, подключенному к внешней сети, на исходящий трафик.
Итоговая конфигурация:
CopyRun
access-list 100 permit ip 192.168.10.0 0.0.0.255 any
access-list 100 deny ip 192.168.20.0 0.0.0.255 any
access-list 100 permit ip any any

interface FastEthernet0/1
 ip access-group 100 out
