# ss-server-systemd

## Install packages

    Install `shadowsocks-libev` from https://github.com/shadowsocks/shadowsocks-libev#install-from-repository-1.
    Or
    Download repo from: https://copr.fedorainfracloud.org/coprs/librehat/shadowsocks/
    e.g.,
    wget https://copr.fedorainfracloud.org/coprs/librehat/shadowsocks/repo/fedora-28/librehat-shadowsocks-fedora-28.repo
    mv librehat-shadowsocks-fedora-28.repo /etc/yum.repos.d/
    dnf copr enable -y librehat/shadowsocks-libev
    dnf install -y shadowsocks-libev

## Firewalld configuration

    firewall-cmd  --add-port=9999/tcp --permanent

## Configure secontext

    setenforce 0

## SS config

    cp ./config.json /etc/shadowsocks-libev/
    Update your desired `port`, `password` etc accordingly.


## Systemd config

    cp shadowsocks.service /etc/systemd/system
    systemctl daemon-reload


## Start/Stop

    systemctl start|stop shadowsocks
    systemctl status shadowsocks

That's it.
