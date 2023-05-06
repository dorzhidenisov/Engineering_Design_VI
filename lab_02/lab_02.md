# Lab 2
* ## hostname
    ```sh
    senku@Senku:~$ hostname
    Senku
    ```
* ## env
    ``` sh
    senku@Senku:~$ env
    SHELL=/bin/bash
    WSL_DISTRO_NAME=Ubuntu
    NAME=Senku
    PWD=/home/senku
    LOGNAME=senku
    MOTD_SHOWN=update-motd
    HOME=/home/senku
    LANG=C.UTF-8
    LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arc=01;31:*.arj=01;31:*.taz=01;31:*.lha=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.tzo=01;31:*.t7z=01;31:*.zip=01;31:*.z=01;31:*.dz=01;31:*.gz=01;31:*.lrz=01;31:*.lz=01;31:*.lzo=01;31:*.xz=01;31:*.zst=01;31:*.tzst=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.alz=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.cab=01;31:*.wim=01;31:*.swm=01;31:*.dwm=01;31:*.esd=01;31:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:
    LESSCLOSE=/usr/bin/lesspipe %s %s
    TERM=xterm-256color
    LESSOPEN=| /usr/bin/lesspipe %s
    USER=senku
    SHLVL=1
    WSLENV=
    XDG_DATA_DIRS=/usr/local/share:/usr/share:/var/lib/snapd/desktop
    PATH=/home/senku/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/mnt/c/Program Files (x86)/Razer Chroma SDK/bin:/mnt/c/Program Files/Razer Chroma SDK/bin:/mnt/c/Program Files (x86)/Razer/ChromaBroadcast/bin:/mnt/c/Program Files/Razer/ChromaBroadcast/bin:/mnt/c/Windows/system32:/mnt/c/Windows:/mnt/c/Windows/System32/Wbem:/mnt/c/Windows/System32/WindowsPowerShell/v1.0/:/mnt/c/Windows/System32/OpenSSH/:/mnt/c/Program Files (x86)/NVIDIA Corporation/PhysX/Common:/mnt/c/Program Files/NVIDIA Corporation/NVIDIA NvDLISR:/mnt/c/Windows/system32/config/systemprofile/AppData/Local/Microsoft/WindowsApps:/mnt/c/Program Files/Git/cmd:/mnt/c/Program Files/Calibre2/:/mnt/c/Program Files/nodejs/:/mnt/c/Program Files/MATLAB/R2023a/runtime/win64:/mnt/c/Program Files/MATLAB/R2023a/bin:/mnt/c/Users/dorzh/AppData/Local/Programs/Python/Python311/Scripts/:/mnt/c/Users/dorzh/AppData/Local/Programs/Python/Python311/:/mnt/c/Users/dorzh/AppData/Local/Microsoft/WindowsApps:/mnt/c/Users/dorzh/AppData/Local/Programs/Microsoft VS Code/bin:/mnt/c/Users/dorzh/AppData/Roaming/npm:/mnt/c/Users/dorzh/AppData/Local/GitHubDesktop/bin:/mnt/c/Program Files (x86)/Windows Kits/10/Debuggers/x64:/mnt/c/msys64/mingw64/bin:/snap/bin
    HOSTTYPE=x86_64
    _=/usr/bin/env
    ```
* ## ps
    ``` sh
    senku@Senku:~$ ps
    PID TTY          TIME CMD
      9 tty1     00:00:00 bash
    106 tty1     00:00:00 ps
    ```
* ## pwd
    ``` sh
    senku@Senku:~$ pwd
    /home/senku
    ```
* ## git clone https://github.com/kevinwlu/iot.git
    ``` sh
    senku@Senku:/mnt/c/codes/design 6$ git clone https://github.com/kevinwlu/iot.git
    Cloning into 'iot'...
    remote: Enumerating objects: 19240, done.
    remote: Counting objects: 100% (289/289), done.
    remote: Compressing objects: 100% (151/151), done.
    remote: Total 19240 (delta 141), reused 187 (delta 93), pack-reused 18951
    Receiving objects: 100% (19240/19240), 27.72 MiB | 7.47 MiB/s, done.
    Resolving deltas: 100% (12840/12840), done.
    Updating files: 100% (393/393), done.
    ```
* ## cd iot
    ```sh
    senku@Senku:/mnt/c/codes/design 6$ cd iot
    senku@Senku:/mnt/c/codes/design 6/iot$ 
    ```
* ## ls
    ```sh
    senku@Senku:/mnt/c/codes/design 6/iot$ ls
    README.md  cases      health  lesson1   lesson2  lesson4  lesson6  lesson8  make      special_problems  systems
    apps       economics  hype    lesson10  lesson3  lesson5  lesson7  lesson9  projects  standards         tools  
    ```
* ## cd
    ```sh
    senku@Senku:/mnt/c/codes/design 6/iot$ cd
    senku@Senku:~$ 
    ```
* ## df
    ```sh
    senku@Senku:~$ df
    Filesystem     1K-blocks      Used Available Use% Mounted on    
    rootfs         976119108 741316552 234802556  76% /
    none           976119108 741316552 234802556  76% /dev
    none           976119108 741316552 234802556  76% /run
    none           976119108 741316552 234802556  76% /run/lock     
    none           976119108 741316552 234802556  76% /run/shm      
    none           976119108 741316552 234802556  76% /run/user     
    tmpfs          976119108 741316552 234802556  76% /sys/fs/cgroup
    C:\            976119108 741316552 234802556  76% /mnt/c  
    ```
* ## mkdir demo & cd demo
    ```sh
    senku@Senku:~$ cd demo
    senku@Senku:~/demo$ 
    ```
* ## nano file
    ![](/lab_02/nano.PNG)
* ## cat file
    ```sh
    senku@Senku:~/demo$ cat file
    lol
    ```
* ## cp, mv
    ```sh
    senku@Senku:~/demo$ cp file file1
    senku@Senku:~/demo$ mv file file2
    senku@Senku:~/demo$ cat file1
    lol
    senku@Senku:~/demo$ cat file2
    lol
    ```
* ## rm file2
    ```sh
    senku@Senku:~/demo$ rm file2 
    senku@Senku:~/demo$ ls
    file1
    ```
* ## clear
    ```sh
    senku@Senku:~/demo$
    ```
* ## man uname
    ![](/lab_02/uname.PNG)
* ## uname -a
    ```sh
    senku@Senku:~/demo$ uname -a
    Linux Senku 4.4.0-19041-Microsoft #2311-Microsoft Tue Nov 08 17:09:00 PST 2022 x86_64 x86_64 x86_64 GNU/Linux
    ```
* ## ifconfig
    ```sh
    eth2: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 26.253.162.37  netmask 255.0.0.0  broadcast 26.255.255.255
            inet6 fdfd::1afd:a225  prefixlen 64  scopeid 0x0<global>
            inet6 fe80::7c89:5cd4:1d33:852d  prefixlen 64  scopeid 0xfd<compat,link,site,host>
            ether 02:50:30:30:1c:c0  (Ethernet)
            RX packets 0  bytes 0 (0.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 0  bytes 0 (0.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

    eth5: flags=65<UP,RUNNING>  mtu 1472
            unspec [NONE SET]  netmask 00-00-00-00-00-00-00-00-00-00-00-00-00-00-00-00        
            inet6 2001:0:2841:f634:284f:67e:ba8a:7feb  prefixlen 64  scopeid 0x0<global>      
            inet6 fe80::284f:67e:ba8a:7feb  prefixlen 64  scopeid 0xfd<compat,link,site,host>
            ether 00:00:00:00:00:00  (Ethernet)
            RX packets 0  bytes 0 (0.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 0  bytes 0 (0.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

    lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 1500
            inet 127.0.0.1  netmask 255.0.0.0
            inet6 ::1  prefixlen 128  scopeid 0xfe<compat,link,site,host>
            loop  (Local Loopback)
            RX packets 0  bytes 0 (0.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 0  bytes 0 (0.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

    wifi0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
            inet 192.168.1.8  netmask 255.255.255.0  broadcast 192.168.1.255
            inet6 fd4b:8d38:69ba:1:a359:fad5:1ef3:6ca2  prefixlen 64  scopeid 0x0<global>
            inet6 fd4b:8d38:69ba:1:942:2e00:be18:b686  prefixlen 128  scopeid 0x0<global>
            inet6 fe80::4cbd:48c5:e2ce:3e22  prefixlen 64  scopeid 0xfd<compat,link,site,host>
            ether b4:69:21:af:9b:0a  (Ethernet)
            RX packets 0  bytes 0 (0.0 B)
            RX errors 0  dropped 0  overruns 0  frame 0
            TX packets 0  bytes 0 (0.0 B)
            TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
    ```
* ## ping localhost
    ```sh
    senku@Senku:~/demo$ ping localhost
    PING localhost (127.0.0.1) 56(84) bytes of data.
    64 bytes from localhost (127.0.0.1): icmp_seq=1 ttl=128 time=0.191 ms
    64 bytes from localhost (127.0.0.1): icmp_seq=2 ttl=128 time=0.180 ms
    64 bytes from localhost (127.0.0.1): icmp_seq=3 ttl=128 time=0.179 ms
    64 bytes from localhost (127.0.0.1): icmp_seq=4 ttl=128 time=0.182 ms
    64 bytes from localhost (127.0.0.1): icmp_seq=5 ttl=128 time=0.189 ms
    ```
* ## netstat
    ```sh
    Active Internet connections (w/o servers)
    Proto Recv-Q Send-Q Local Address           Foreign Address         State
    Active UNIX domain sockets (w/o servers)
    Proto RefCnt Flags       Type       State         I-Node   Path
    ```