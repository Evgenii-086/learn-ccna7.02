
---

> **ВАЖНО**
> 
> Форма для ответов на вопросы будет доступна только при развертывании лабораторной работы 

---

## Задачи

**Часть 1. Изучение DNS-преобразования URL в IP-адрес**

**Часть 2. Изучение поиска в DNS с помощью команды nslookup на веб-сайте**

**Часть 3: Изучение поиска в DNS с помощью команды nslookup на почтовых серверах**

## Общие сведения/сценарий

Систему доменных имен (Domain Name System - DNS) используют при вводе унифицированного указателя ресурса (URL-адреса), например, **http://www.cisco.com**, в поле адреса веб-обозревателя. В первой части URL-адреса указывается используемый протокол. Наиболее распространенные протоколы — это HTTP (протокол передачи гипертекста), HTTPS (протокол передачи гипертекста по шифрованному каналу) и FTP (протокол передачи файлов).

Система DNS использует вторую часть URL-адреса, в приведенном примере — www.cisco.com. DNS доменное имя в IP-адрес, позволяющий узлу-источнику связаться с сервером. В ходе этой лабораторной работы вы посмотрите, как работает DNS, и воспользуетесь командой nslookup (поиск на сервере имен), чтобы получить дополнительную информацию о DNS.

## Необходимые ресурсы

-   1 компьютер (Windows с доступом в Интернет и командной строкой)

## Инструкции

### **Часть 1. Изучение DNS-преобразования URL в IP-адрес**

1.  Откройте командную строку Windows.
2.  Введите эхо-запрос с помощью команды ping для URL-адреса Корпорации по присвоению имен и номеров в Интернете (ICANN) **www.icann.org**. ICANN координирует DNS, IP-адреса, управление системой доменных имен верхнего уровня и функции управления системой корневого сервера. Компьютер должен преобразовать www.icann.net в IP-адрес, чтобы определить, куда отправлять пакеты протокола ICMP (протокола управления сообщениями в сети Интернет).

В первой строке выходных данных отображается доменное имя **www.icann.org**, преобразованное в IP-адрес. Результаты работы DNS должны быть видны, даже если в вашем учреждении межсетевой экран блокирует обмен пакетами по команде ping или если сервер назначения не принимает эхо-запросы с помощью команды ping.

**Примечание**. Если доменное имя преобразовано в адрес IPv6, используйте команду `ping -4 www.icann.org` для его перевода в адрес IPv4 (при необходимости).

Запишите IP-адрес сайта [www.icann.org](http://www.icann.org).

**Введите ваш ответ здесь.**

3.  Вместо URL-адреса введите в адресную строку браузера IPv4-адрес, полученный при выполнении **шага 2**. Например, **https://192.0.32.7**. Если ваш компьютер имеет IPv6 адрес, вы можете ввести IPv6 адрес, например, **[2620:0:2d0:200::7](https://2620:0:2d0:200::7)**.
4.  Обратите внимание, что домашняя веб-страница ICANN отображается без использования DNS.

Большинству людей проще запоминать слова, чем цифры. Адрес веб-сайта **www.icann.org** запомнят с гораздо большей вероятностью, чем IP-адрес 192.0.32.7. Компьютеры оперируют числами, причем в двоичной системе. DNS переводит слова в числа. IP-адрес, который в десятичной системе счисления выглядит как 192.0.32.7, в двоичной системе будет иметь вид 11000000.00000000.00100000.00000111. Что произойдет, если скопировать эти цифры двоичной системы и вставить их в адресную строку браузера?

5.  Через окно командной строки отправьте эхо-запрос на веб-сайт **www.cisco.com**.

**Примечание**. Если доменное имя преобразовано в адрес IPv6, используйте команду `ping -4 www.cisco.com` для его перевода в адрес IPv4 (при необходимости).

```
C:\> ping www.cisco.com
C:\> ping -4 www.cisco.com
```

При отправке эхо-запроса с помощью команды `ping` на www.cisco.com выдается такой же IP-адрес, как в примере, или другой? Дайте пояснение.

**Введите ваш ответ здесь.**

Введите IP-адрес, полученный после отправки эхо-запроса командой `ping` на www.cisco.com, в адресную строку браузера. Отображается ли веб-сайт? Дайте пояснение.

**Введите ваш ответ здесь.**

### **Часть 2. Изучение поиска в DNS с помощью команды nslookup на веб-сайте**

1.  В командной строке введите команду `nslookup`. Результат будет отличаться от примера.

```
C:\> nslookup
```

Вопрос:

Какой DNS-сервер используется по умолчанию?

**Введите ваш ответ здесь.**

2.  Обратите внимание на изменение командной строки: появился символ «больше» (\>). Это командная строка `nslookup`. Здесь можно вводить команды, относящиеся к системе DNS.

В командной строке введите «?», чтобы просмотреть список всех команд, доступных в режиме `nslookup`.

3.  В строке nslookup введите **www.cisco.com**.

```
>www.cisco.com
Default Server: one.one.one.one
Address: 1.1.1.1

Не заслуживающий доверия ответ:
Name: e2867.dsca.akamaiedge.net
Адреса: 2600:1404:a:395::b33
          2600:1404:a:38e:::b33
          172.230.155.162
Aliases: www.cisco.com
          www.cisco.com.akadns.net
          wwwds.cisco.com.edgekey.net
          wwwds.cisco.com.edgekey.net.globalredir.akadns.net
```

Вопросы:

Назовите преобразованный IPv4-адрес.

**Введите ваш ответ здесь.**

**Примечание**. Возможно, что в вашем месте нахождения IP-адрес будет отличаться, поскольку Cisco использует зеркальные серверы, расположенные в разных странах.

Совпадает ли он с адресом из выходных данных команды ping?

**Введите ваш ответ здесь.**

Под адресами, помимо IP-адреса 172.230.155.162, есть следующие номера: 2600:1404:a:395::b33 и 2600:1404:a:38e::b33. Что они значат?

**Введите ваш ответ здесь.**

4.  В командной строке nslookup введите IP-адрес только что обнаруженного веб-сервера Cisco. С помощью команды `nslookup` можно узнать доменное имя IP-адреса, если URL-адрес не известен.

```
> 172.230.155.162
Сервер по умолчанию : one.one.one.one
Address: 1.1.1.1

Name: a172-230-155-162.deploy.static.akamaitechnologies.com
Address: 172.230.155.162
```

Утилита **nslookup** преобразовывает доменные имена в IP-адреса и наоборот.

Вопрос:

Пользуясь утилитой nslookup, запишите IP-адреса, связанные с веб-сайтом [**www.google.com**](http://www.google.com)**.**

**Введите ваш ответ здесь.**

### **Часть 3. Изучение поиска в DNS с помощью команды nslookup на почтовых серверах**

1.  В командной строке nslookup введите `set type=mx`, чтобы с помощью команды nslookup определить почтовые серверы.

```
> set type=mx
```

2.  В строке nslookup введите **cisco.com**.

```
> cisco.com
Server: one.one.one.one
Address: 1.1.1.1

Не заслуживающий доверия ответ:
cisco.com MX preference = 20, mail exchanger = rcdn-mx-01.cisco.com
cisco.com MX preference = 30, mail exchanger = aer-mx-01.cisco.com
cisco.com MX preference = 10, mail exchanger = alln-mx-01.cisco.com
```

Основной принцип сетевой архитектуры — резервирование (настройка сразу нескольких почтовых серверов). Если один из почтовых серверов недоступен, компьютер, выполняющий запрос, попытается обратиться ко второму серверу. Администраторы электронной почты устанавливают очередность обращения к почтовым серверам с помощью параметра **MX preference**. Сначала запрос отправляется на почтовый сервер, для которого указано наименьшее значение **MX preference**.

Исходя из приведенных выше результатов, какой почтовый сервер будет запрошен первым при отправке электронного сообщения на **cisco.com**?

**Введите ваш ответ здесь.**

3.  В командной строке утилиты nslookup введите команду `exit`, чтобы вернуться к обычной командной строке компьютера.
4.  В командной строке компьютера введите команду `ipconfig /all`.

Вопрос:

Запишите IP-адреса всех используемых в локальной сети DNS-серверов.

**Введите ваш ответ здесь.**

## Вопрос для повторения

В чем основное назначение DNS?

**Введите ваш ответ здесь.**
