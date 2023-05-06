# Lab 5
* ## Install Mosquitto
    ```sh
    pi@raspberrypi:~ $ sudo apt install mosquitto mosquitto-clients
    senku@Senku:/mnt/c/codes/design 6/Engineering_Design_VI$ 
    pi@raspberrypi:~ $ mosquitto_sub -h localhost -v -t "\$SYS/#"
    $SYS/broker/version mosquitto version 1.5.7
    $SYS/broker/uptime 22 seconds
    $SYS/broker/clients/total 0
    $SYS/broker/clients/inactive 0
    $SYS/broker/clients/disconnected 0
    $SYS/broker/clients/active 0
    $SYS/broker/clients/connected 0
    $SYS/broker/clients/expired 0
    $SYS/broker/load/messages/received/1min 0.00
    $SYS/broker/load/messages/received/5min 0.00
    $SYS/broker/load/messages/received/15min 0.00
    $SYS/broker/load/messages/sent/1min 0.00
    $SYS/broker/load/messages/sent/5min 0.00
    $SYS/broker/load/messages/sent/15min 0.00
    $SYS/broker/load/publish/dropped/1min 0.00
    $SYS/broker/load/publish/dropped/5min 0.00
    $SYS/broker/load/publish/dropped/15min 0.00
    $SYS/broker/load/publish/received/1min 0.00
    $SYS/broker/load/publish/received/5min 0.00
    $SYS/broker/load/publish/received/15min 0.00
    $SYS/broker/load/publish/sent/1min 0.00
    $SYS/broker/load/publish/sent/5min 0.00
    $SYS/broker/load/publish/sent/15min 0.00
    $SYS/broker/load/bytes/received/1min 0.00
    $SYS/broker/load/bytes/received/5min 0.00
    $SYS/broker/load/bytes/received/15min 0.00
    $SYS/broker/load/bytes/sent/1min 0.00
    $SYS/broker/load/bytes/sent/5min 0.00
    $SYS/broker/load/bytes/sent/15min 0.00
    $SYS/broker/load/sockets/1min 0.00
    $SYS/broker/load/sockets/5min 0.00
    $SYS/broker/load/sockets/15min 0.00
    $SYS/broker/load/connections/1min 0.00
    $SYS/broker/load/connections/5min 0.00
    $SYS/broker/load/connections/15min 0.00
    $SYS/broker/messages/stored 51
    $SYS/broker/messages/received 0
    $SYS/broker/messages/sent 0
    $SYS/broker/store/messages/count 51
    $SYS/broker/store/messages/bytes 176
    $SYS/broker/subscriptions/count 0
    $SYS/broker/retained messages/count 51
    $SYS/broker/heap/current 23348
    $SYS/broker/heap/maximum 23576
    $SYS/broker/publish/messages/dropped 0
    $SYS/broker/publish/messages/received 0
    $SYS/broker/publish/messages/sent 0
    $SYS/broker/publish/bytes/received 0
    $SYS/broker/publish/bytes/sent 0
    $SYS/broker/bytes/received 0
    $SYS/broker/bytes/sent 0
    pi@raspberrypi:~ $ service mosquitto status
    ● mosquitto.service - Mosquitto MQTT v3.1/v3.1.1 Broker
    Loaded: loaded (/lib/systemd/system/mosquitto.service; enabled; vendor pr   Active: active (running) since Sat 2023-05-06 07:12:16 EDT; 59s ago      
        Docs: man:mosquitto.conf(5)
            man:mosquitto(8)
    Main PID: 4858 (mosquitto)
        Tasks: 1 (limit: 4915)
    CGroup: /system.slice/mosquitto.service
            └─4858 /usr/sbin/mosquitto -c /etc/mosquitto/mosquitto.conf      

    May 06 07:12:16 raspberrypi systemd[1]: Starting Mosquitto MQTT v3.1/v3.1.1 
    May 06 07:12:16 raspberrypi systemd[1]: Started Mosquitto MQTT v3.1/v3.1.1 Blines 1-12/12 (END)
    pi@raspberrypi:~ $ netstat -tln
    Active Internet connections (only servers)
    Proto Recv-Q Send-Q Local Address           Foreign Address         State   

    tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN  

    tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN  

    tcp        0      0 127.0.0.1:25            0.0.0.0:*               LISTEN  

    tcp        0      0 0.0.0.0:1883            0.0.0.0:*               LISTEN  

    tcp6       0      0 :::22                   :::*                    LISTEN  

    tcp6       0      0 ::1:631                 :::*                    LISTEN  

    tcp6       0      0 ::1:25                  :::*                    LISTEN  

    tcp6       0      0 :::1883                 :::*                    LISTEN
    ```
* ## Terminal 1
    ```sh
    pi@raspberrypi:~ $ mosquitto_sub -h localhost -v -t test/topic &
    [1] 5602
    pi@raspberrypi:~ $ test/topic Hello
    ```
* ## Terminal 2
    ```sh
    pi@raspberrypi:~ $ mosquitto_pub -h localhost -t test/topic -m "Hello"
    ```
* ## Install Paho and run code to subscribe on one terminal and publish on another
    ```sh
    pi@raspberrypi:~/iot/lesson5 $ python3 client.py
    Connected with result code 0
    $SYS/broker/publish/bytes/received 166344411810
    $SYS/broker/publish/bytes/sent 2388567644042
    $SYS/broker/publish/messages/dropped 152481692032
    $SYS/broker/publish/messages/received 741439591
    $SYS/broker/publish/messages/sent 18906481642
    $SYS/broker/publish/messages/dropped 152492404438
    $SYS/broker/publish/messages/received 741454607
    $SYS/broker/publish/messages/sent 18907072470
    $SYS/broker/publish/bytes/received 166349487031
    $SYS/broker/publish/bytes/sent 2388665012349
    ```
* ## Terminal 1
    ```sh
    pi@raspberrypi:~/iot/lesson5 $ python3 sub.py
    Connected with result code 0
    paho/test Hello
    ```
* ## Terminal 2
    ``` sh
    pi@raspberrypi:~/iot/lesson5 $ python3 pub.py
    ```
* ## Terminal 1
    ```sh
    pi@raspberrypi:~/iot/lesson5 $ python3 sub-multiple.py
    Connected with result code 0
    paho/test/multiple multiple 1
    paho/test/multiple multiple 2
    ```
* ## Terminal 2
    ``` sh
    pi@raspberrypi:~/iot/lesson5 $ python3 pub-multiple.py
    ```
* ## Terminal 1
    ```sh
    pi@raspberrypi:~/iot/lesson5 $ python3 subcpu.py
    Connected with result code 0
    MyCPU 2023-05-06 07:46:38
    MyCPU CPU Usage:   8.7 %
    MyCPU 2023-05-06 07:46:48
    MyCPU CPU Usage:   0.4 %
    ```
* ## Terminal 2
    ``` sh
    pi@raspberrypi:~/iot/lesson5 $ python3 pubcpu.py
    2023-05-06 07:46:38
    CPU Usage:   8.7 %
    2023-05-06 07:46:48
    CPU Usage:   0.4 %
    ```
* ## Terminal 1
    ```sh
    pi@raspberrypi:~/demo $ cp ~/iot/lesson5/subraspi.py .
    pi@raspberrypi:~/demo $ nano subraspi.py
    pi@raspberrypi:~/demo $ python3 subraspi.py
    Connected with result code 0
    raspberrypi 2023-05-06 07:50:59
    raspberrypi Temperature: 34.0 C
    raspberrypi CPU Usage:   2.0 %
    raspberrypi 2023-05-06 07:51:09
    raspberrypi Temperature: 34.5 C
    raspberrypi CPU Usage:   0.1 %
    raspberrypi 2023-05-06 07:51:19
    raspberrypi Temperature: 33.6 C
    raspberrypi CPU Usage:   0.2 %
    ```
* ## Terminal 2
    ``` sh
    pi@raspberrypi:~/demo $ cp ~/iot/lesson5/system_info.py .
    pi@raspberrypi:~/demo $ cp ~/iot/lesson5/pubraspi.py .
    pi@raspberrypi:~/demo $ nano pubraspi.py
    pi@raspberrypi:~/demo $ python3 pubraspi.py
    Free RAM: 99 (3827)
    Number of processes: 160
    Up time:  1:08
    Number of connections: 5
    Temperature in C: 34.5
    IP-address: 192.168.1.5
    CPU speed in MHz: arm_freq=1500

    2023-05-06 07:50:59
    Temperature: 34.0 C
    CPU Usage:   2.0 %
    2023-05-06 07:51:09
    Temperature: 34.5 C
    CPU Usage:   0.1 %
    2023-05-06 07:51:19
    Temperature: 33.6 C
    CPU Usage:   0.2 %
    ```