---
title: Linux基础命令1：管理用户
date: 2023-01-28 00:00:01
categories:
- 运维
tags:
- Linux
- useradd
---

## 一.用户管理基本操作
### 1.创建用户
```
# useradd wps
```
### 2.设置密码
方法一：交互式
```
# passwd wps
```
方法二：非交互式
```
# echo 123 | passwd --stdin wps
```

### 3.修改id

创建时指定主组
```
# useradd -g groupname wps
```

创建是指定附加组
```
# useradd -G groupname wps
```

创建时指定uid
```
# useradd -u 4000 wps
```
### 4.修改创建好的用户信息
- usermod [选项] username
- 选项 
  - -l 新用户名
  - -L 锁定用户账户
  - -U 解锁用户账户
  - -e 修改过期时间
  - -G 组名： 修改附加组
  - -d 路径：更改用户主目录

### 5.删除用户
添加-r宿主目录/用户邮件也一并删除
```
# userdel -r wps
```

### 6.查询用户id
```
# id wps
```


## 二.禁止用户登录系统的几种方法

方法一:禁止外部登录，通过内部su可以登录
```
# passwd -l wps
```

方法二：禁止外部登录，通过内部su可以登录
```
# usermod -L wps
```

方法三：彻底禁止登录
```
# usermod -s wps /sbin/nologin
```

方法四：进入/etc/passwd修改

方法五：禁止不包含root通过外部所有账号登录，内部可以登录
```
# touch /etc/nologin
```

