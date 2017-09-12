# ss-server-systemd

## Firewalld configuration

    firewall-cmd  --add-port=9999/tcp --permanent


## SS config

    cp ./config.json /etc/shadowsocks-libev/
    Update your desired `port`, `password` etc accordingly.


## Systemd config

    cp shadowsocks.service /etc/systemd/system
    systemctl daemon-reload


## Start/Stop

    systemctl start|stop shadowsocks
    systemctl status shadowsocks
