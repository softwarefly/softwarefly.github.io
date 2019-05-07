---
layout: post
title: Run MySQL in a Docker Container with Persistent Local Data
categories: Deployment
description: Run MySQL in a Docker Container with Persistent Local Data
keywords: Docker, MySQL, Persistence
---

## 普通安装

### 1. 下载镜像，mysql 5.7

```sh
$ docker pull mysql:5.7
```

### 2. 创建mysql容器，并后台启动

```sh
$ docker run -d -p 3306:3306 -e MYSQL_USER="woniu" -e MYSQL_PASSWORD="123456" -e MYSQL_ROOT_PASSWORD="123456" --name mysqltest1 mysql:5.7 --character-set-server=utf8 --collation-server=utf8_general_ci
```

**参数说明：**

-e MYSQL_USER="woniu"：添加woniu用户

-e MYSQL_PASSWORD="123456"：设置添加的用户密码

-e MYSQL_ROOT_PASSWORD="123456"：设置root用户密码

--character-set-server=utf8：设置字符集为utf8

--collation-server=utf8_general_cli：设置字符比较规则为utf8_general_cli

## 挂载外部配置和数据安装

### 1. 创建目录和配置文件my.cnf

```sh
mkdir /docker
mkdir /docker/mysql
mkdir /docker/mysql/conf
mkdir /docker/mysql/data
 
创建my.cnf配置文件
touch /docker/mysql/conf/my.cnf
 
my.cnf添加如下内容：
[mysqld]
user=mysql
character-set-server=utf8
default_authentication_plugin=mysql_native_password
[client]
default-character-set=utf8
[mysql]
default-character-set=utf8
```

### 2. 创建容器，并后台启动

```sh
$ docker run -d -p 3306:3306 --privileged=true -v /docker/mysql/conf/my.cnf:/etc/mysql/my.cnf -v /docker/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 --name mysqltest2 mysql:5.7
```

**参数说明：**

--privileged=true：容器内的root拥有真正root权限，否则容器内root只是外部普通用户权限

-v /docker/mysql/conf/my.cnf:/etc/my.cnf：映射配置文件

-v /docker/mysql/data:/var/lib/mysql：映射数据目录

## Reference

* [【Docker】：使用docker安装mysql，挂载外部配置和数据][1]
* [Docker 安装 MySQL][2]
* [How to Run MySQL in a Docker Container on macOS with Persistent Local Data][3]
* [How to share data between a Docker container and host][4]
* [More Topics on Deploying MySQL Server with Docker][5]
* [test_db][6]

[1]: https://blog.csdn.net/woniu211111/article/details/80968154
[2]: https://www.twle.cn/l/yufei/docker/docker-basic-install-mysql.html
[3]: https://medium.com/@crmcmullen/how-to-run-mysql-in-a-docker-container-on-macos-with-persistent-local-data-58b89aec496a
[4]: https://www.techrepublic.com/article/how-to-share-data-between-a-docker-container-and-host/
[5]: https://dev.mysql.com/doc/refman/8.0/en/docker-mysql-more-topics.html
[6]: https://github.com/datacharmer/test_db