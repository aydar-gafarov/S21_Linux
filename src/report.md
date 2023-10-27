# 1. Установка OC
>cat /etc/issue

P.S: У меня мак на М1, сюда можно поставить только 22.04.
![](./png/1.png)
# 2. Создание нового пользователя
>• sudo adduser halleyju122

>• sudo usermod -g adm halleyju122

![](./png/2.png)
>• cat etc/passwd | grep user

![](./png/3.png)
# 3. Настройка сети ОС
>• sudo hostnamctl set-hostname user-1

![](./png/4.png)

#### Устанавливаем временную зону
>• sudo timedatectl set-timezone Europe/Samara

![](./png/5.png)
 
#### Сетевые адреса 
![](./png/6.png)

На системах Unix интерфейс loopback обычно имеет имя lo.
Интерфейс loopback имеет несколько путей применения. Он может быть использован сетевым клиентским программным обеспечением, чтобы общаться с серверным приложением, расположенным на том же компьютере.

![](./png/7.png)

Dynamic Host Configuration Protocol (DHCP) — автоматический предоставляет IP адреса и прочие настройки сети (маску сети, шлюз и т.п) компьютерам и различным устройствам в сети.



> Внешний IP-адрес шлюза

![](./png/8.png) 

> Внутренний IP-адрес шлюза

![](./png/9.png)

>• cd etc/netplan

>• sudo nano 00-installer-config.yaml

![](./png/10.png)
>• sudo netplan generate

>• sudo netplan apply

>• reboot

![](./png/11.png)
![](./png/12.png)

# 4. Обновление ОС
>• sudo apt update
![](./png/13.png)

# 5. Использование команды sudo

Sudo — это утилита, предоставляющая привилегии root для выполнения административных операций в соответствии со своими настройками. Она позволяет легко контролировать доступ к важным приложениям в системе.
>• sudo usermodd -a -G sudo new_user

>• sudo hostnamectl set-hostname new_hostname

![](./png/15.png)

# 6. Установка и настройка службы времени
>• sudo timedatectl

>• timedatectl show

![](./png/16.png)

# 7. Установка и использование текстовых редакторов

#### Скачиваем текстовые редакторы 
>• sudo apt install mcedit

>• sudo apt install nano

>• sudo apt install vim

![](./png/17.png)

##### VIM 




![](./png/18.png)
![](./png/19.png)
>:wq - выход с сохранением

##### NANO
![](./png/20.png)
![](./png/21.png)

>Cmd + x + y + enter  - сохранение и выход

##### MCEDIT
![](./png/22.png)
![](./png/23.png)

>Esc + 2 + 10 - сохранение и выход

##### VIM





![](./png/24.png)
![](./png/25.png)
>:!q - выход без сохранения

##### NANO
![](./png/26.png)
![](./png/27.png)
>Cmd + n - выход без сохранения

##### MCEDIT
![](./png/28.png)
![](./png/29.png)
>Esc + 10 + NO - выход без сохранения

##### VIM
![](./png/30.png)
![](./png/31.png)
>Esc + : s /find word/to do - найти и заменить

##### NANO
![](./png/32.png)
![](./png/33.png)
>Cmd + w - найти, cmd + \ - заменить

##### MCEDIT
![](./png/34.png)
![](./png/35.png)
>Esc + 7 - найти, esc + 4 - заменить

# 8. Установка и базовая настройка сервиса SSHD

>• sudo apt-get install ssh

>• sudo apt install openssh-server

![](./png/36.png)
![](./png/37.png)

>• ssh-status

![](./png/38.png)

>• sudo nano /etc/ssh/sshd_config

![](./png/39.png)

![](./png/40.png)


•	ps (показывает запущенные процессы, выполняемые пользователем в окне терминала);

•	ps -e или ps -A (Чтобы просмотреть все запущенные процессы);

•	ps -d (Чтобы показать все процессы, кроме лидеров сессии);

•	ps -d -N (можно инвертировать вывод с помощью переключателя -N. Например, если хочу вывести только лидеров сеансов);

•	ps T (увидеть только процессы, связанные с этим терминалом);

•	ps r (просмотреть все работающие (running) процессы);

NETSTAT

>netstat -tan

![](./png/41.png)
•	-t (--tcp) отображает соедниеня только по tcp;

•	-a (--all) вывод всех активных подключений TCP;

•	-n (--numeric) вывод активных подключений TCP с отображением адресов и номеров портов в числовом формате;

•	Proto: Название протокола (протокол TCP или протокол UDP);

•	recv-Q: очередь получения сети;

•	send-Q: Сетевая очередь отправки;

•	Local Address адрес локального компьтера и используемы номер порта;

•	Foreign Address адрес и номер удаленного компьтера к которомц подключен сокет;

•	State состояние сокетв;

•	0.0.0.0 означает IP-адрес на локальной машине;

# 9. Установка и использование утилит top, htop
#### TOP
•	uptime - 15min;

•	количество авторизованных пользователей - 1;

•	общую загрузку системы - 0.00, 0.01, 0.00;

•	общее количество процессов - 106;

•	загрузку cpu - 0.0%;

•	загрузку памяти - 163/1967;

•	pid процесса занимающего больше всего памяти - 1029(top -o %MEM);

•	pid процесса, занимающего больше всего процессорного времени - 1029 (top -o %CPU);

![](./png/42.png)

#### HTOP
>PID

![](./png/43.png)
>CPU

![](./png/44.png)

>MEM 

![](./png/45.png)

>TIME

![](./png/46.png)

>SSHD

![](./png/47.png)

>SYSLOG

![](./png/48.png)

>+hostname, clock, uptime

![](./png/49.png)

# 10. Использование утилиты fdisk

>fdisk -I

![](./png/50.png)
•   Название жесткого диска Ubuntu 22.04 Sch;

•   Размер 64 GB;

•   Количество секторов 134217728;

•   Размер swap 2 GB;

# 11. Использование утилиты df

>df 

![](./png/51.png)
•	размер раздела - 31270768;

•	размер занятого пространства - 5176368;

•	размер свободного пространства - 24480372;

•	процент использования - 18-%;


>df -Th

![](./png/52.png)
•	размер раздела - 30G;

•	размер занятого пространства - 5.0G;

•	размер свободного пространства - 24G;

•	процент использования - 18%

# 12. Использование утилиты du
>• sudo du -sh /home /var/log /var

В байтах
![](./png/53.png)

>• sudo du -s --block-size=1 /home /var/log /var

В человекочитаемом виде
![](./png/54.png)

>• sudo du var/log/*

![](./png/55.png)

# 13. Установка и использование утилиты ncdu

>• sudo apt-get install ncdu

>• ncdu home

![](./png/56.png)

>• ncdu var 

![](./png/57.png)

>• ncdu var/log

![](./png/58.png)

# 14. Работа с системными журналами

>• sudo nano var/log/dmesg

>• sudo nano var/log/syslog

>• sudo nano var/log/auth.log

Last login

![](./png/59.png)

SSHD restart
>• sudo systemctl restart ssh

>• grep "ssh" /var/log/syslog

![](./png/60.png)

# 15. Использование планировщика заданий CRON

>uptime

![](./png/61.png)

![](./png/62.png)

![](./png/63.png)