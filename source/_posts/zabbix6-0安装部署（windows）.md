title: zabbix6.0安装部署（windows）
author: wps
date: 2023-02-02 11:52:31
categories:
- 运维
tags:

---

windows下安装zabbix监控有两种方法

## 免安装下载后解压，修改配置文件
一.下载安装zabbix agents

压缩包解压另存为zabbix
![](https://tudingtu.cn/i/2023/02/02/nnp4il.png)

二.修改配置文件

1.打开zabbix_agentd.conf添加IP地址和主机名称

在Server=后添加zabbix server的IP地址
![](https://tudingtu.cn/i/2023/02/02/nzbcku.png)
在Hostname=后面添加主机名
![](https://great.wzznft.com/i/2023/02/02/nzygp9.png)

2.复制二进制文件\bin\zabbix_agentd.exe和修改好的配置文件\conf\zabbix_agentd.conf到文件根目录下
![](https://great.wzznft.com/i/2023/02/02/o3jhmg.png)

2.将zbbix agent安装为windos服务
打开cmd输入下面的命令

``` cmd
f:\zabbix\zabbix_agentd.exe -c -i f:\zabbix\zabbix_agentd.conf
```
三.添加windows主机

## 手动安装
安装过程中进行配置和Zabbix服务器的连接信息

注意：安装时需要正确填写Zabbix服务器的Host name和IP地址

Host name需要和Zabbix服务端Web页面上设置的主机名称一致