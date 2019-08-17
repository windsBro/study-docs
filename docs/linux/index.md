## centOS

### 开放防火墙
```markdown
配置文件：/etc/firewalld/
查看版本：firewall-cmd --version
查看帮助：firewall-cmd --help
查看区域信息：firewall-cmd --get-active-zones
查看指定接口所属区域信息：firewall-cmd --get-zone-of-interface=eth0
拒绝所有包：firewall-cmd --panic-on
取消拒绝状态：firewall-cmd --panic-off
查看是否拒绝：firewall-cmd --query-panic

查看防火墙状态：firewall-cmd --state
开启防火墙：systemctl start firewalld 
关闭防火墙：systemctl stop firewalld
设置开机启动：systemctl enable firewalld
停止并禁用开机启动：sytemctl disable firewalld
重启防火墙：firewall-cmd --reload

查看指定区域所有开启的端口号
firewall-cmd --zone=public --list-ports

在指定区域开启端口(如80端口号，命令方式)
firewall-cmd --zone=public --add-port=80/tcp --permanent
重新启动防火墙
firewall-cmd --reload

参数说明：
–zone 作用域
–add-port=8080/tcp 添加端口，格式为：端口/通讯协议
–permanent #永久生效，没有此参数重启后失效

在指定区域开启某个范围的端口号(如18881~65534，命令方式)
firewall-cmd --zone=public --add-port=18881:65534/tcp --permanent
重新启动防火墙
firewall-cmd --reload
```
### 安装mysql