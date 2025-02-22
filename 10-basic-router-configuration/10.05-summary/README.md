<!-- verified: agorbachev 03.05.2022 -->

<!-- 10.4.5 -->
## Настройка исходных параметров маршрутизатора

При настройке начальных параметров маршрутизатора необходимо выполнить следующие задачи.

1.  Настройте имя устройства.
2.  Обеспечьте безопасность привилегированного режима EXEC.
3.  Обеспечьте безопасность доступа к пользовательскому режиму EXEC
4.  Обеспечьте безопасность удаленного доступа по протоколу Telnet или SSH
5.  Защитите все пароли в файле конфигурации.
6.  Создайте баннер с правовым уведомлением.
7.  Сохраните конфигурацию.

## Настройка интерфейсов

Чтобы маршрутизаторы были доступны, настройте их интерфейсы. Маршрутизатор Cisco ISR 4321 оснащен двумя интерфейсами Gigabit Ethernet: GigabitEthernet 0/0/0 (G0/0/0) и GigabitEthernet 0/0/1 (G0/0/1). Настройка интерфейса маршрутизатора очень похожа на управление SVI на коммутаторе. С помощью команды **no shutdown** активируется интерфейс. 

Чтобы активировать физический уровень, интерфейс должен быть также подключен к другому устройству (коммутатору или маршрутизатору). Для проверки конфигурации можно использовать команды **show ip interface brief** и **show ipv6 interface brief**, **show ip route** и **show ipv6 route**, так же как **show interfaces**, **show ip interface** и **show ipv6 interface.**

## Настройка шлюза по умолчанию

Чтобы оконечное устройство могло обмениваться данными по сети, присвойте ему правильный IP-адрес, включая адрес шлюза по умолчанию. Адреса шлюза по умолчанию и интерфейса маршрутизатора для роутера, который подключен к локальной сети хоста, обычно совпадают. IP-адрес узлового устройства и адрес интерфейса маршрутизатора должны находиться в одной сети. 

Чтобы подключить коммутатор и управлять им через локальную IP-сеть, настройте виртуальный интерфейс коммутатора (SVI). SVI настроен с IPv4-адресом и маской подсети в локальной сети. Коммутатор также должен иметь адрес шлюза по умолчанию, настроенный для удаленного управления из другой сети. Чтобы настроить шлюз IPv4 по умолчанию на коммутаторе, используйте команду глобальной конфигурации  **ip default-gateway ip-address**. Используйте IPv4-адрес локального интерфейса маршрутизатора, подключенного к коммутатору.

<!-- 10.4.6 -->
<!-- quiz -->

