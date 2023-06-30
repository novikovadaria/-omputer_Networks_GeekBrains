# Computer Networks (seminars)
## Lesson 1. Fundamentals of Computer Networks. Ethernet.
Fix the network from the file https://disk.yandex.ru/d/pxY6JoEJ8AHhew), so that all links are green. Ping the computers.
Submit two screenshots of successful pinging from PC 10.0.0.1 to the server interface Fa0 10.0.0.5 and to PC 10.0.0.3.
Submit one screenshot of successful pinging from PC 192.168.0.2 to the server interface Fa1 192.168.0.1

## Lesson 2. Ethernet Technology. IP Protocol.
Practice video (https://disk.yandex.ru/i/uXIIMwm32thOJQ)
Commands for Cisco IOS - https://disk.yandex.ru/d/PwxEU3KrArG8Zw

Conditions:

Set up the network according to the diagram in the file https://disk.yandex.ru/d/1m4aUoqDm1SKBQ
Check the operation of neighboring networks with the ping command.
Circle all broadcast domains in blue
4*. Set up loopback interfaces.
Submit screenshots:
with green links
successful pings between a couple of neighboring networks (neighboring networks are Connected networks to one router)
output of any ARP table
(Tasks marked with * are tasks of increased complexity and require self-study. If they are not completed, it does not affect the grade)

## Lesson 3. Ethernet Technology. IP Protocol.
Conditions:

We complicate the network from the previous homework
Using only static routing, connect the network of computers and server
Check the operation of the network with the ping command from computers to the server and back
2.1* Try to set up static so that all interfaces are pinged from everywhere.
Study the resulting routing tables
Practice using the tracert command
6*. Set up loop back interfaces, statics to them, and they should also be pinged
(Tasks marked with * and * are tasks of increased complexity. If they are not completed, it does not affect the grade).
Submit screenshots with a successful trace between the networks (if only p.2 is done then a screenshot of a trace from a computer to a server, if p.2.1 is done then add a screenshot of a trace from a computer to intermediate networks, which are between the computer and the server).
## Lesson 5. Basics of Computer Networks. Transport Layer. UDP and TCP.
In the attached file "The Ultimate PCAP.pcap" (from the distributed material) find an e-mail. What's inside the email and who is it for?
Consolidate filtering skills. Start a trace to 8.8.8.8. Capture it in Wireshark. Analyze.

Consolidate filtering skills. Find another unencrypted site with the ability to enter a login/password. (you can configure the corresponding output in Google by request with the key "-inurl:https" at the end). Capture them in Wireshark, building a filter.

*. On the site https://launchpad.net/ubuntu/+archivemirrors mirrors with Ubuntu images are presented by countries. Download a small file (for example, ls-lR.gz) from Chile and Yandex. Take two dumps for each download. Analyze the download speed and look at tcptrace. Estimate the average RTT and look for the maximum RWND for the downloader.
Provide screenshots of speed charts and tcptrace. Is there a difference? What is it?

Before the next seminar, watch the practice (https://disk.yandex.ru/i/6pAvRRMrK2e7jw )

Lesson 6. Basics of Computer Networks. Transport Layer. UDP and TCP.
Write your server program and run it.
Start several clients. Simulate a chat.
Send me the code of the written server (you can through github, if convenient, or right here in txt format) and screenshots of the working chat.
Track the sockets with the netstat command. (also send a screenshot of your chat sockets)

## Lesson 7. NAT. GRE.
Condition:

Set up the network according to the diagram in the file
https://disk.yandex.ru/d/hegGC7woXSjz0g where:
Office 1 - network 10.1.1.0/24
Office 2 - network 10.0.0.0/16
Office 3 - network 172.16.0.0/16
Office 4 - network 192.168.145.0/24
Where "Internet" - there is an imitation of the Internet using OSPF, you choose public networks between routers yourself.
Task 1. Set up Port Forwarding on servers in Office 2. Server0 should provide HTTP on port 80, and Server1 should provide HTTPS on port 443. The pages should be different.

Task 2. Set up PAT in Office 3 for computers so that they go to the Internet under one public IP address on Router1.

Provide a screenshot of open pages on HTTP and HTTPS to the public address of Router3 in the web browser of Office3 clients (with PC1 and PC0)

Then provide the output show ip nat translation c Router1.

Task 3. Connect the networks Office 1 and Office 4 using GRE. Provide a trace from Laptop0 to Server2.

Task 4. Finish up OpenVPN (or Wireguard) if you didn't have time. Provide a screenshot of the public IP before and after connecting via VPN + screenshot of the output of the ip addr command.
Please note that in Yandex Cloud there are two nuances:

if you create an interruptible machine, then the public address will change after reboot
on the machine Yandex makes a private IP, but at the same time in the virtualization a Static NAT 1:1 is created in your public IP.
Lesson 8. Basics of HTTP/HTTPS and DNS
Set up the network according to the information in the diagram
(https://disk.yandex.ru/d/Vaxkf2X0RG9NGw .)
Simulate "Internet" using OSPF. There should be no private networks in routing.
Provide access to the "Internet" for computers from Office 1 using PAT.
Open access from the "Internet" to servers from Office 2 using Port Forwarding.
For computers from Office 1, different sites should open via HTTP and HTTPS from Office 2 with one domain name.

Provide screenshots of different sites opened with one domain name.
# Компьютерные сети (семинары)
## Урок 1. Основы компьютерных сетей. Ethernet.
Починить сеть из файла https://disk.yandex.ru/d/pxY6JoEJ8AHhew), чтобы все линки были зеленые. Попинговать компьютеры.
Сдать два скриншота успешного пинга с РС 10.0.0.1 на интерфейс сервера Fa0 10.0.0.5 и на PC 10.0.0.3.
Сдать один скриншот успешного пинга с РС 192.168.0.2 на интерфейс сервера Fa1 192.168.0.1
## Урок 2. Технология Ethernet. Протокол IP.
Видео с практикой (https://disk.yandex.ru/i/uXIIMwm32thOJQ)
команды для Cisco IOS - https://disk.yandex.ru/d/PwxEU3KrArG8Zw

Условие:
1. Настроить сеть согласно схеме в файле https://disk.yandex.ru/d/1m4aUoqDm1SKBQ
2. Проверить работоспособность соседних между собой сетей командой ping.
3. Обвести синим все broadcast домены
4*. Настроить loopback интерфейсы.
Скинуть скриншоты:
с зелеными линками
успешные пинги между парой-тройкой соседних сетей (соседние сети - это Connected сети к одному роутеру)
вывод любой таблицы ARP

(Задание со * являются заданиями с повышенной сложностью и требуют самостоятельного изучения. Если они не выполнены, это не влияет на оценку)

## Урок 3. Технология Ethernet. Протокол IP.
Условие:
1. Усложняем сеть из предыдущего домашнего задания
Используя только статическую маршрутизацию связать сеть компов и сервера
2. Проверить работоспособность сети командой ping с компов до сервера и обратно
2.1* Попробовать настроить статику так, чтобы пинговались все интерфейсы отовсюду.
3. Изучить получившиеся таблицы маршрутизации
4. Попрактиковаться в использовании команды tracert
6*. Настроить loop back интерфейсы, статику до них и они тоже должны пинговаться
(Задание со * и * являются заданиями с повышенной сложностью. Если они не выполнены, это не влияет на оценку).

Скинуть скриншоты с успешным трейсом между сетями (если сделан только п.2 то скрин трейса от компа до сервера, если сделан п.2.1 то добавьте скрин трейса от компа до промежуточных сетей, которые лежат между компом и сервером).
## Урок 4. Основы компьютерных сетей. Сетевой уровень. Протоколы маршрутизации. VLAN.
Условие:
1. Настроить сеть согласно схеме в файле с помощью OSPF и VLAN. Починить неработающие линки.
https://disk.yandex.ru/d/IQdns-ljqsBFFg
2. Убедиться что трафик от компов до сервера ходит через два маршрута с помощью ЕСМР.
3. Скинуть скриншот с таблицей маршрутизации с r1. Должны быть сети Connected для VLAN’ов.
4. Поймать трейс на любом компе, когда он пойдет через r5. Удалить один из линков на r5. Снова сделать трейс, убедиться что трафик пошел по резервному пути. Скинуть скриншот с разными трейсами.
Скинуть еще один скриншот с изменившейся таблицей маршрутизации с r1.
## Урок 5. Основы компьютерных сетей. Транспортный уровень. UDP и TCP.
В приложенном файле “The Ultimate PCAP.pcap” (из раздаточного материала) найти e-mail. Что внутри письма и для кого оно?
Закрепите навыки фильтрования. Запустите трейс до 8.8.8.8. И перехватите его в Wireshark. Проанализируйте.

Закрепите навыки фильтрования. Найдите еще один сайт без шифрования с возможностью ввода логина/пароля. (можно в гугл настроить соответствующую выдачу по запросу с ключом “-inurl:https” в конце). Перехватите их в Wiresharke, построив фильтр.

*. На сайте https://launchpad.net/ubuntu/+archivemirrors представлены зеркала с образами Убунту по странам. Скачайте небольшой файл (например ls-lR.gz) из Чили и с Яндекса. Снимите два дампа для каждого скачивания. Проанализируйте скорость скачивания и посмотрите tcptrace. Прикиньте средний RTT и поищите максимальный RWND для скачивающего.
Предоставить скриншоты графиков скорости и tcptrace. Есть ли разница? В чем она?

Перед следующим семинаром посмотрите практику (https://disk.yandex.ru/i/6pAvRRMrK2e7jw )
## Урок 6. Основы компьютерных сетей. Транспортный уровень. UDP и TCP.
Напишите свою программу сервер и запустите её.
Запустите несколько клиентов. Сымитируйте чат.
Отправьте мне код написанного сервера (можете через github, если удобно или прямо здесь в txt формате) и скриншоты работающего чата.
Отследите сокеты с помощью команды netstat. (тоже пришлите скриншот именно сокетов вашего чата)

## Урок 7. NAT. GRE.
Условие:
1. Настроить сеть согласно схеме в файле
https://disk.yandex.ru/d/hegGC7woXSjz0g где:
Office 1 - cеть 10.1.1.0/24
Office 2 - cеть 10.0.0.0/16
Office 3 - cеть 172.16.0.0/16
Office 4 - cеть 192.168.145.0/24
Где “Интернет” - там имитация Интернета с помощью OSPF, выберите сами публичные сети между роутерами.

Задача 1. Настроить на Port Forwarding на сервера в Office 2. Server0 должен предоставлять HTTP по 80му порту, а Server1 должен предоставлять HTTPS по 443 порту. Странички должны быть разные.

Задача 2. Настроить PAT в Office 3 для компьютеров, чтобы они выходили в интернет под одним публичным IP адресом на Router1.

Предоставить скриншот открытых страниц по HTTP и HTTPS по публичному адресу Router3 в веб-браузере клиентов Office3 (с РС1 и РС0)

После чего предоставить вывод show ip nat translation c Router1.

Задача 3. Связать сети Office 1 и Office 4 с помощью GRE. Предоставит трейс с Laptop0 до Server2.

Задача 4. Доделать OpenVPN (или Wireguard) если не успели. Предоставит скриншот публичного IP до и после подключения через VPN + скриншот вывода команды ip addr.
Учтите что в Yandex Cloud есть два нюанса:
- если создавать прерываемую машину, то публичный адрес будет меняться после перезапуска
- на машине Yandex делает приватный IP, но одновременно в виртуализации создается Static NAT 1:1 в ваш публичный IP.

## Урок 8. Основы HTTP/HTTPS и DNS
Настроить сеть согласно информации на схеме
(https://disk.yandex.ru/d/Vaxkf2X0RG9NGw .)
Сымитировать "Интернет" с помощью OSPF. Приватных сетей в маршрутизации быть не должно.
Для компьютеров из Office 1 предоставить доступ в "Интернет" с помощью PAT.
Открыть доступ из "Интернета" к серверам из Office 2 c помощью Port Forwarding.
Для компьютеров из Office 1 должны открываться разные сайты по HTTP и HTTPS из Office 2 по одному доменному имени.

Предоставить скриншоты открытых разных сайтов по одному доменному имени.

Предоставить скриншот таблицы NAT трансляций с Router3.

Предоставить скриншот таблицы маршрутизации с Router0.

