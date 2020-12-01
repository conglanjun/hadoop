## hadoop 学习
### 环境搭建
- ubuntu 1804 安装vmware，下载CentOS-7-x86_64-Minimal-2009.iso。
- 虚拟机启动后执行命令。
```shell
vi /etc/sysconfig/network-scripts/ifcfg-ens33

设置
ONBOOT=yes # 机器启动的时候激活网卡

配置dns
vi /etc/resolv.conf
nameserver 8.8.8.8

重启网络
service network restart

yum install -y vim net-tools
```
- clone虚拟机node02，node03

|IP|主机名|
|----|-----|
|192.168.150.100|node01|
|192.168.150.101|node02|
|192.168.150.102|node03|

```shell
vi /etc/sysconfig/network-scripts/ifcfg-ens33

#配置mac地址。查看vm中网络配置高级中mac地址
HWADDR=00:0C:29:95:24:41
...
BOOTPROTO=static
BROADCAST=192.168.150.255
IPADDR=192.168.150.100
NETMASK=255.255.255.0
GATEWAY=192.168.150.2

node01 02 03都要配置MAC地址。

# 配置网络，MAC地址，静态IP
vim /etc/sysconfig/network-scripts/ifcfg-ens33
HWADDR=00:0C:29:95:24:41
TYPE=Ethernet
PROXY_METHOD=none
BROWSER_ONLY=no
BOOTPROTO=static
BROADCAST=192.168.150.255
IPADDR=192.168.150.100
NETMASK=255.255.255.0
GATEWAY=192.168.150.2
DEFROUTE=yes
IPV4_FAILURE_FATAL=no
IPV6INIT=yes
IPV6_AUTOCONF=yes
IPV6_DEFROUTE=yes
IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
NAME=ens33
UUID=3395b089-ab8f-48a9-8716-2837dba693c2
DEVICE=ens33
ONBOOT=yes
```

