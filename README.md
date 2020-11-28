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
