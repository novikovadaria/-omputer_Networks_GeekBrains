### Task 1:

Настроить NAT в схеме [s5_demonstration_NAT.pkt](s5_demonstration_NAT.pkt)

### Task 2:

Настроить GRE в схеме [s5_demonstration_GRE.pkt](s5_demonstration_GRE.pkt)

### Task 3:

Настроить Open VPN

### Solution:

##### Task 1:

1. Заходим в Router2 -> CLI, в конфиг интерфейса `interface gigabitEthernet 0/0/1` <br>
    он находится во внутренней части сети и будет выполнять роль `inside` стороны <br>
    вводим `ip nat inside`, и выходим `ex`. Заходим в следующий интерфейс `interface gigabitEthernet 0/0/0` <br>
    он выполняет роль `outside` так как находится на внешней стороне сети (которая смотрит в интернет) <br>
    вводим `ip nat outside`, и выходим `ex`. В глобал конфиге настраиваем NAT <br> 
    `ip nat inside source static 10.0.0.100 7.7.7.1`, <br>
    здесь у нас выбор static, list (один в один, или несколько в один), далее указываем IP адрес устройства <br>
    внутренней сети (компьютер, сервер), и IP адрес (публичный) сети в интернете. <br>
    командой `sh ip nat translations` можем посмотреть "перебросы" <br>
    ![1.jpg](img%2F1.jpg)
2. Заходим на Router0 -> CLI, `interface gigabitEthernet 0/0/1` -> `ip nat inside` -> `ex`, <br>
   `interface gigabitEthernet 0/0/0` -> `ip nat outside` -> `ex`, настраиваем NAT <br>
    для начала создадим Access List (который хранит в себе список IP адресов), <br>
    `ip access-list standart NET_10` -> `permit 10.0.0.0 0.0.0.255` -> `ex`<br>
    (standart означает что мы проверяем только source IP, extended и source и destination) <br>
    `ip nat inside source list NET_10 interface gigabitEthernet 0/0/0 overload` <br>
   (выбираем interface потому что у нас один публичный IP в который будем NAT'ить, если было бы несколько, то pull)<br>
   (выбираем наружний интерфейс) <br>
    заходим с PC0 на веб адрес `http://7.7.7.1` и `https://7.7.7.1`, `sh ip nat translations` <br>
    ![2.jpg](img%2F2.jpg)
3. Заходим на Router0 -> CLI, `interface gigabitEthernet 0/0/1` -> `ip nat inside` -> `ex`, <br>
   `interface gigabitEthernet 0/0/0` -> `ip nat outside` -> `ex`, настраиваем NAT <br>
    `ip nat inside source static tcp 10.0.0.100 80 6.6.6.1 80` <br>
   (прописываем inside IP сервера и порт 80, затем публичный IP и порт 80, потому что http) <br>
    `ip nat inside source static tcp 10.0.0.101 443 6.6.6.1 443` <br>
   (аналогично для второго сервера но на порт 443, так как он работает с https) <br>
    ![3.jpg](img%2F3.jpg) <br>
    ![4.jpg](img%2F4.jpg) <br>
    ![5.jpg](img%2F5.jpg)

#### Task 2:

1. Заходим на Router0 -> CLI -> `en` -> `conf t` -> `interface tunnel 777` (создаём новый виртуальный интерфейс с <br>
    номером 777) -> `do sh run` -> ![6.jpg](img%2F6.jpg) -> `ip address 172.16.0.1 255.255.255.0` <br>
   (прописываем IP адрес для интерфейса, это вспомогательный IP для тунелирования) -> <br>
    -> `tunnel source gigabitEthernet 0/0/1` (указываем интерфейс из которого будут выходить пакеты с доп L3 <br>
    заголовком) -> `tunnel destination 4.4.4.2` (указываем публичный IP адрес, который будет принимать наше <br>
    тунелирование) -> ![7.jpg](img%2F7.jpg) -> так как пакеты с PC0/PC1 отправленные в сеть 192.168.0.0/24 <br>
    дойдут до Router0 на интерфейс Gig0/0/0 и в первую очередь что сделает роутер будет смотреть таблицу <br>
    маршрутизации в целях поиска сети 192.168.0.0/24, а её там нет, поэтому её надо добавить маршрут по умолчанию <br>
    `ex` -> `ip route 192.168.0.0 255.255.255.0 172.16.0.2` (маршрут в сеть производится за некстхопом с IP <br>
    вспомогательной сети на destination роутере) -> ![8.jpg](img%2F8.jpg)
2. На Router4 делаем встречные настройки -> CLI -> `en` -> `conf t` -> `interface tunnel 777` -> <br>
    -> `ip address 172.16.0.2 255.255.255.0` -> `tunnel source gigabitEthernet 0/0/0` -> <br>
    -> `tunnel destination 1.1.1.1` -> `ex` -> `ip route 192.168.0.0 255.255.255.0 172.16.0.1` <br>
    `sh int tu 777` <br>
    ![9.jpg](img%2F9.jpg) <br>
    ![10.jpg](img%2F10.jpg) <br>
    ![11.jpg](img%2F11.jpg) <br>
    ![12.jpg](img%2F12.jpg)

#### Task 3:

1. `apt update && apt -y install ca-certificates wget net-tools gnupg`
2. `wget https://as-repository.openvpn.net/as-repo-public.asc -qO /etc/apt/trusted.gpg.d/as-repository.asc`
3. `echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/as-repository.asc] http://as-repository.openvpn.net/as/debian jammy main">/etc/apt/sources.list.d/openvpn-as-repo.list`
4. `apt update && apt -y install openvpn-as` <br>
    ![open_vpn.jpg](..%2FHomework_7%2Fimg%2Fopen_vpn.jpg)