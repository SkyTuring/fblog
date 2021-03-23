---
title: docker安装软件
date: 2021-03-19 18:21:59 
summary: 用docker安装一些常用软件，好用的软件
cover: false
top: false
categories: 
  - 软件
tags: 
  - docker
---
### wikijs

```shell
docker run -d -p 8080:3000 --name wiki \
--restart unless-stopped \
-e "DB_TYPE=mysql" \
-e "DB_HOST=ip" \
-e "DB_PORT=33306" \
-e "DB_USER=user" \
-e "DB_PASS=pass" \
-e "DB_NAME=wiki" requarks/wiki
```