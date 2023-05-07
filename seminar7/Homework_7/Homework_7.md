# Task 7:

Условие:

1. Настроить сеть согласно схеме в файле <br>
   [s5_homework.pkt](s5_homework.pkt) где: <br>
   Office 1 - cеть 10.1.1.0/24 <br>
   Office 2 - cеть 10.0.0.0/16 <br>
   Office 3 - cеть 172.16.0.0/16 <br>
   Office 4 - cеть 192.168.145.0/24 <br>
   Где “Интернет” - там имитация Интернета с помощью OSPF, выберите сами публичные сети между роутерами.<br>
   <br>
Задача 1. Настроить на Port Forwarding на сервера в Office 2. Server0 должен предоставлять HTTP по 80му порту,<br>
а Server1 должен предоставлять HTTPS по 443 порту. Странички должны быть разные.<br>
   <br>
Задача 2. Настроить PAT в Office 3 для компьютеров, чтобы они выходили в интернет под одним публичным IP адресом на<br>
Router1. <br>
   <br>
Предоставить скриншот открытых страниц по HTTP и HTTPS по публичному адресу Router3 в веб-браузере клиентов Office3<br>
(с РС1 и РС0)<br>
   <br>
После чего предоставить вывод show ip nat translation c Router1.<br>
   <br>
Задача 3. Связать сети Office 1 и Office 4 с помощью GRE. Предоставит трейс с Laptop0 до Server2.<br>
   <br>
Задача 4. Доделать OpenVPN (или Wireguard) если не успели. Предоставит скриншот публичного IP до и после подключения<br>
через VPN + скриншот вывода команды ip addr.<br>
Учтите что в Yandex Cloud есть два нюанса:<br>
   <br>
- если создавать прерываемую машину, то публичный адрес будет меняться после перезапуска<br>
- на машине Yandex делает приватный IP, но одновременно в виртуализации создается Static NAT 1:1 в ваш публичный IP.

### Solution :

1. Настроить сеть: <br>
   ![network_all.jpg](img%2Fnetwork_all.jpg) <br>
2. Настроить на Port Forwarding на серваки: <br>
   Вэб странички на оба сервака: <br>
   ![HTTP_HTTPS.jpg](img%2FHTTP_HTTPS.jpg) <br>
   show ip nat translation c Router1 <br>
   ![NAT_translation.jpg](img%2FNAT_translation.jpg) <br>
3. Связать сети Office 1 и Office 4 с помощью GRE. Предоставит трейс с Laptop0 до Server2: <br>
   ![tracert_by_tunnel.jpg](img%2Ftracert_by_tunnel.jpg) <br>
4. OpenVPN. <br>
   ![yandex_v.jpg](img%2Fyandex_v.jpg) <br>
   ![open_vpn.jpg](img%2Fopen_vpn.jpg)