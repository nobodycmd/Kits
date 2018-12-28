#centos 7
* curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
* python get-pip.py
* pip install shadowsocks
* vim /etc/shadowsocks.json
~~~
{
    "server":"0.0.0.0",
    "server_port":50013,
    "local_port":1080,
    "password":"1234567890",
    "timeout":600,
    "method":"aes-256-cfb"
}
~~~
* vim /etc/systemd/system/shadowsocks.service  将shadowsocks加入系统服务
~~~
[Unit]
Description=Shadowsocks
[Service]
TimeoutStartSec=0
ExecStart=/usr/bin/ssserver -c /etc/shadowsocks.json
[Install]
WantedBy=multi-user.target
~~~
* systemctl enable shadowsocks   开机启动 shadowsocks 服务
* systemctl start shadowsocks    立即启动 shadowsocks 服务
