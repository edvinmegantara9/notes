# manjaro

## remove unused package

    pacman -Qdt
    pacman -Scc

## update aur package

    trizen -Syua

## battery: status

    upower --dump

## bluetooth start service

    sudo systemctl start bluetooth

## bluetooth show configuration

    cat /etc/bluetooth/main.conf

## remote rdp

    xfreerdp /v:192.168.0.132 /u:skai

# routing: add routing

    sudo ip route add xx.xx.xx.x/24 via 192.168.0.1 metric 100 dev wlp3s0
    sudo ip route add xx.xx.xx.x/24 via 192.168.0.1 dev wlp3s0
    ip route show

# nvidia: run nvidia graphic on manjaro

    sudo optirun -b none nvidia-settings -c :8
    dmesg | grep bbswitch
    glxgears -info
    sudo optirun glxgears -info
    sudo primusrun glxgears -info
    sudo primusrun steam steam://rungameid/570 -info

# github

## clone repository

    git clone https://github.com/USERNAME/REPOSITORY_NAME.git

## reset local, ambil dari repository remote

    git reset --hard origin/master
    git pull

# flutter

## flutter connect device

    adb tcpip 5555
    adb connect device_ip_address

## launch multiple device flutter

    flutter run -d all

## build app bundle for smaller size

    flutter build appbundle

## flutter web

    flutter build web
    cd build/web/
    python -m http.server 8000
    firebase deploy

## run relase mode

    flutter run --release
    flutter run --profile

# laravel: start in homestead

    vagrant up --provision
    vagrant ssh
    php -S 192.168.10.10:8000 -t public

# ngrok: start services

    ngrok http 192.168.10.10:8000 -host-header=saharga.dev

# docker

## start services

    sudo systemctl start docker

## remove file docker

    var/lib/docker
    docker system prune -a

# node js: run npm

    sudo npm start

# react-native: additional setting

    typerscript error
        javasript.validate: disable
    add local.properties in android/gradle/wrapper
        sdk.dir = /home/echo/Android/Sdk
    edit gradle version in android/gradle/wrapper/gradle-wrapper.properties
        distributionUrl=https\://services.gradle.org/distributions/gradle-6.3-all.zip

# keychorn: k6 fix ubs fn keys

    echo 0 | sudo tee /sys/module/hid_apple/parameters/fnmode
    https://www.reddit.com/r/MechanicalKeyboards/comments/d5io49/keychron_k2_f_keys_dont_work_w_linux_help/

# ubuntu server

## access via ssh

    ssh username@192.168.xxx.xxx -p 22

## install ftp

    sudo apt install vsftpd
    sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.echo
    sudo nano /etc/vsftpd.conf
    write_enable=YES
    chroot_local_user=YES
    allow_writeable_chroot=YES
    sudo systemctl restart vsftpd
    sudo systemctl status vsftpd
    https://musaamin.web.id/cara-install-ftp-server-dengan-vsftpd-di-ubuntu/

## server log

    more /var/log/auth.log
    more /var/log/syslog
    sudo more vsftpd.log
    lastlog

## timezone set

    sudo timedatectl set-timezone Asia/Jakarta

# kali linux

## nmap

    nmap -h
        manual page
    nmap -v -sS -O 192.168.43.2
        -v  : untuk verbose supaya banyak keluar informasi
        -sS : scanning port dengan mengirim paket SYNC
        -O  : guess OS detection
    nmap -oN hasilNmap.txt 192.168.43.2
        create nmap file output
    nmap -sP 192.168.43.2/24
        discover host
    nmap -sA 192.168.43.2
        find out if host is protected by a firewall
    nmap -PN 192.168.43.2
        scan if firewall active
    nmap --iflist
        show ip/route
    sudo nmap -p21 -script ftp-brute.nse -script-args \ userdb=/usr/share/wordlists/nmap.lst,passdb=/usr/share/wordlists/nmap.lst 192.168.43.2
        ftp brute force
