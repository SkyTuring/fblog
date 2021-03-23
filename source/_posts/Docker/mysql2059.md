---
title: navicat连接mysql出现2059错误
date: 2021-03-19 18:21:59 
summary: 2059错误
cover: false
top: false
categories: 
  - 软件
tags: 
  - docker
  - mysql
---

错误出现的原因是在mysql8之前的版本中加密规则为mysql_native_password，而在mysql8以后的加密规则为caching_sha2_password。

解决此问题有两种方法，一种是更新navicat驱动来解决此问题，一种是将mysql用户登录的加密规则修改为mysql_native_password。建议采取了第二种方式：

用管理员权限打开cmd，输入mysql -u root -p进入输入密码后进入mysql数据库；

进入数据库

```sql
mysql -u root -p
use mysql
```

修改加密规则

```sql
ALTER USER 'root'@'%' IDENTIFIED BY 'yourpassword' PASSWORD EXPIRE NEVER; 
```

修改密码

```sql
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY 'yourpassword'; 
```

刷新数据

```sql
FLUSH PRIVILEGES; 
```

