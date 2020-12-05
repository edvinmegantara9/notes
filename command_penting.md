# start ngrok services
    ngrok http 192.168.10.10:8000 -host-header=saharga.dev

# start laravel/lumen in homestead
    vagrant up --provision
    vagrant ssh
    php -S 192.168.10.10:8000 -t public

# start bluetooth service
    sudo systemctl start bluetooth

# start docker services
    sudo systemctl start docker

# github reset local, ambil dari repository remote
    git reset --hard origin/master
    git pull

# run npm
    sudo npm start

# flutter connect device
    adb tcpip 5555
    adb connect device_ip_address

# launch multiple device flutter
    flutter run -d all

# flutter web
    flutter build web
    cd build/web/
    python -m http.server 8000
    firebase deploy

    flutter build appbundle

# run relase mode
    flutter run --release
    flutter run --profile

# update aur package
    trizen -Syua

# remove unused package in manjaro
    pacman -Qdt
    pacman -Scc

# run nvidia setting
    optirun -b none nvidia-settings -c :8

# remote rdp
    xfreerdp /v:192.168.0.132 /u:skai

# docker
    var/lib/docker
    docker system prune -a

# run nvidia graphic manjaro
    sudo optirun -b none nvidia-settings -c :8
    dmesg | grep bbswitch
    glxgears -info
    sudo optirun glxgears -info
    sudo primusrun glxgears -info
    sudo primusrun steam steam://rungameid/570 -info

# battery status
    upower --dump

# setting bluetooth
    cat /etc/bluetooth/main.conf

# routing to wincore
    sudo ip route add xx.xx.xx.x/24 via 192.168.0.1 metric 100 dev wlp3s0
    sudo ip route add xx.xx.xx.x/24 via 192.168.0.1 dev wlp3s0
    ip route show

# react native additional setting
    typerscript error
        javasript.validate: disable
    add local.properties in android/gradle/wrapper
        sdk.dir = /home/echo/Android/Sdk
    edit gradle version in android/gradle/wrapper/gradle-wrapper.properties
        distributionUrl=https\://services.gradle.org/distributions/gradle-6.3-all.zip

# keychorn k6 fix ubs fn keys
    echo 0 | sudo tee /sys/module/hid_apple/parameters/fnmode
    https://www.reddit.com/r/MechanicalKeyboards/comments/d5io49/keychron_k2_f_keys_dont_work_w_linux_help/
