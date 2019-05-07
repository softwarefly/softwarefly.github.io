---
layout: post
title: Start a Remote MySQL Server with Docker
categories: Deployment
description: Start a Remote MySQL Server with Docker
keywords: Docker, MySQL
---


## 1. 下载MySQL的Docker镜像

```sh
$ docker search mysql (搜索MySQL镜像)  
$ docker pull mysql （下载mysql镜像，默认最新版本）
```

## 2. 运行镜像

设置root账号初始密码（123456），映射本地宿主机端口3306到Docker端口3306。测试过程没有挂载本地数据盘：

```sh
$ docker run -it --rm --name mysql -e MYSQL_ROOT_PASSWORD=123456 -p 3306:3306 -d mysql  
```

Docker mysql 把数据存储在本地目录，很简单，只需要映射本地目录到容器即可

```sh
# 指定数据目录
$ docker run -d -e MYSQL_ROOT_PASSWORD=123456 --name mysql -v /data/mysql/data:/var/lib/mysql -p 3306:3306 mysql 
```

```sh
# 指定数据目录和配置文件
$ docker run -d -e MYSQL_ROOT_PASSWORD=123456 --name mysql -v /data/mysql/my.cnf:/etc/mysql/my.cnf -v /data/mysql/data:/var/lib/mysql -p 3306:3306 mysql 
```



## 3. 查看已运行的容器

```sh
$ docker ps -a
```
<div align="left">
<img src = "/images/posts/deployment/docker-ps.jpg" width = "2302"/>
</div>

## 4. 进入mysql容器

```sh
$ docker exec -it mysql bash
root@28ddb46a15b8:/#
```

## 5. 容器内登陆Mysql

```sh
root@28ddb46a15b8:/# mysql -uroot -p123456
```

<div align="left">
<img src = "/images/posts/deployment/docker-mysql-login.jpg" width = "500"/>
</div>

## 6. 查看用户信息

```sh
mysql> select host,user,plugin,authentication_string from mysql.user;  
```

<div align="left">
<img src = "/images/posts/deployment/mysql-usr-info.jpg" width = "800"/>
</div>

备注：host为 % 表示不限制ip，localhost表示本机使用，plugin非`mysql_native_password` 则需要修改密码

## 7. 修改密码

```sh
% ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '<password>';
% ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '<password>';
mysql> ALTER user 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456';(自己修改数据库密码)
mysql> FLUSH PRIVILEGES;
```

## 8. Navicat连接数据库

<div align="left">
<img src = "/images/posts/deployment/navicat-access-mysql.png" width = "800"/>
</div>

## Reference

* [docker 安装MySQL远程连接（阿里云服务器）][1]
* [Start a Remote MySQL Server with Docker quickly][2]
* [How to Create a MySql Instance with Docker Compose][3]
* [How to Run MySQL in a Docker Container on macOS with Persistent Local Data][4]
* [Docker 安装 MySQL][5]

[1]: https://blog.csdn.net/weixin_42242494/article/details/80630267
[2]: https://medium.com/@backslash112/start-a-remote-mysql-server-with-docker-quickly-9fdff22d23fd
[3]: https://medium.com/@chrischuck35/how-to-create-a-mysql-instance-with-docker-compose-1598f3cc1bee
[4]: https://medium.com/@crmcmullen/how-to-run-mysql-in-a-docker-container-on-macos-with-persistent-local-data-58b89aec496a
[5]: http://www.runoob.com/docker/docker-install-mysql.html

