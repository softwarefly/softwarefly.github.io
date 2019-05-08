---
layout: post
title: Run Oracle in a Docker Container with Persistent Local Data
categories: Deployment
description: Run Oracle in a Docker Container with Persistent Local Data
keywords: Docker, Oracle
---

**目录**

* TOC
{:toc}

## 安装镜像

在Docker Hub中搜索镜像并安装 

```sh
$ docker search oracle12c
$ docker pull sath89/oracle-12c
```

或者，从本地镜像文件载入

```sh
$ docker load < sath89_oracle-12c.tar.xz
```

查看镜像

```sh
[root@VM_0_13_centos ~]# docker images
REPOSITORY             TAG                 IMAGE ID            CREATED             SIZE
sath89/oracle-12c      latest              ee3351d51185        9 months ago        5.7GB
```

## 创建容器

创建并运行容器的三种方式

* 直接运行在8080和1521端口

```sh
$ docker run -d -p 8080:8080 -p 1521:1521 sath89/oracle-12c
```

* 在主机上运行数据并能够重用

```sh
$ docker run -d -p 8080:8080 -p 1521:1521 -v /docker/oracle/data:/u01/app/oracle sath89/oracle-12c
```

* 使用自定于的DBCA_TOTAL_MEMORY运行

```sh
$ docker run -d -p 8080:8080 -p 1521:1521 -v /docker/oracle/data:/u01/app/oracle -e DBCA_TOTAL_MEMORY=1024 sath89/oracle-12c
```

这里使用第二种，第二种可以把创建的数据库保存在本地，这里我先创建一个文件夹用于持久保存数据。

```sh
$ mkdir -p /docker/oracle/data  //create directory 
```

创建并运行数据库实例，需要等待较长的时间

```sh
$ docker run -d -p 8080:8080 -p 1521:1521 -v /docker/oracle/data:/u01/app/oracle sath89/oracle-12c
81d5d58574c08b0f35fa57e7c1ff1cc06e8f1bcb918d42887de2bee5d83ad119
```

运行上述命令会有一串字母，这里可以通过这串字母查看创建期间的日志

```sh
$ docker logs -f 81d5d58574c08b0f35fa57e7c1ff1cc06e8f1bcb918d42887de2bee5d83ad119
Database not initialized. Initializing database.
Starting tnslsnr
Copying database files
1% complete
3% complete
11% complete
18% complete
26% complete
33% complete
37% complete
Creating and starting Oracle instance
40% complete
45% complete
50% complete
55% complete
56% complete
60% complete
62% complete
Completing Database Creation
66% complete
70% complete
73% complete
85% complete
96% complete
100% complete
Look at the log file "/u01/app/oracle/cfgtoollogs/dbca/xe/xe.log" for further details.
Configuring Apex console
Database initialized. Please visit http://#containeer:8080/em http://#containeer:8080/apex for extra configuration if needed
Starting web management console

PL/SQL procedure successfully completed.

Starting import from '/docker-entrypoint-initdb.d':
found file /docker-entrypoint-initdb.d//docker-entrypoint-initdb.d/*
[IMPORT] /entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*

Import finished

Database ready to use. Enjoy! 😉
```

查看实例运行情况

```sh
$ docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                PORTS                                            NAMES
b81304f41bdf        sath89/oracle-12c   "/entrypoint.sh "   13 hours ago        Up 13 hours           0.0.0.0:1521->1521/tcp, 0.0.0.0:8080->8080/tcp   tender_cartwright
```

Navicat测试连接情况


<div align="left">
<img src = "/images/posts/deployment/navicat-to-oracle.png"/>
</div>

## 进入容器

```sh
[root@VM_0_13_centos ~]$ docker exec -it b81304f41bdf /bin/bash 
root@b81304f41bdf:/$ . oraenv
ORACLE_SID = [xe] ? 
The Oracle base has been set to /u01/app/oracle
root@b81304f41bdf:/$ sqlplus / as sysdba    #sqlplus sys/<your password>@//localhost:1521/<your SID> as sysdba

SQL*Plus: Release 12.1.0.2.0 Production on Wed May 8 02:55:09 2019

Copyright (c) 1982, 2014, Oracle.  All rights reserved.

ERROR:
ORA-01017: invalid username/password; logon denied

Enter user-name: system
Enter password: 
Last Successful login time: Wed May 08 2019 02:23:16 +00:00

Connected to:
Oracle Database 12c Standard Edition Release 12.1.0.2.0 - 64bit Production

SQL>  
```
默认参数：

* `sid`: xe
* `service name`: xe
* `username`: system
* `password`: oracle

## Oracle配置

使用pl/sql连接时需要配置tnsname
```vim
VISTUAL =
  (DESCRIPTION =
    (ADDRESS_LIST =
      (ADDRESS = (PROTOCOL = TCP)(HOST = 192.168.xx.xx)(PORT = 1521))
    )
    (CONNECT_DATA =
      (SERVICE_NAME = xe)
    )
  )
```

* 修改密码

```sql
SQL> alter user system identified by oracle; /*修改用户 system 的密码为 oracle，可自定义*/
```

* 创建表空间

创建表空间核用户，这个可以使用工具连接到oracle数据库上进行创建，也可以手动命令行进行创建。注意依然是在sysdba权限下操作,命令如下：

```sql
SQL> select name from v$tempfile;    /*查询临时表空间的路径*/
NAME
--------------------------------------------------------------------------------
/u01/app/oracle/oradata/xe/temp01.dbf

SQL> 
```
创建表空间，名：test，数据文件路径复制临时表空间数据文件路径然后改一下文件名就行了，大小：1G， 自动增长：50M 。 参数根据自己的需求自行修改

```sql
SQL> create tablespace test datafile '/u01/app/oracle/oradata/xe/test.dbf' size 1G reuse autoextend on next 50M maxsize unlimited default storage(initial 128k next 128k minextents 2 maxextents unlimited);

Tablespace created.
```
查看所有表空间，看看是否有刚才创建的
```sql
SQL> select tablespace_name from dba_tablespaces;

TABLESPACE_NAME
------------------------------
SYSTEM
SYSAUX
UNDOTBS1
TEMP
USERS
TEST

6 rows selected.
```

创建用户，test01，密码：testpass，设置默认表空间为刚才创建的 test， 临时表空间设为默认的 TEMP

```sql
SQL> create user test01 identified by testpasswd default tablespace TEST temporary tablespace TEMP;

User created.
```

查看用户名，可以看到是否有刚才我们创建的用户名
```sql
SQL> select username from dba_users;

USERNAME
--------------------------------------------------------------------------------
TEST01
SCOTT
ORACLE_OCM
OJVMSYS
SYSKM
XS$NULL
GSMCATUSER
MDDATA
SYSBACKUP
DIP
SYSDG

11 rows selected.

```

授权用户 test01，拥有连接，管理员，导入，导出权限，并可以传递权限。（根据需求自己定义权限）

```sql
SQL> grant connect,dba,exp_full_database,imp_full_database to test01 with admin option;

Grant succeeded.

```

## 导入导出数据

* 数据拷贝

```sh
$ docker cp test.dmp b81304f41bdf:/u01/app/oracle/
```

* 导入数据

```sql
root@b81304f41bdf:/home/oracle$ imp system/oracle@123.207.x.x/xe file=/u01/app/oracle/test.dmp ignore=y full=y

Import: Release 12.1.0.2.0 - Production on Wed May 8 02:21:35 2019

Copyright (c) 1982, 2015, Oracle and/or its affiliates.  All rights reserved.


Connected to: Oracle Database 12c Standard Edition Release 12.1.0.2.0 - 64bit Production

Export file created by EXPORT:V10.02.01 via conventional path

Warning: the objects were exported by ZHANGZHONG, not by you

import done in US7ASCII character set and AL16UTF16 NCHAR character set
import server uses AL32UTF8 character set (possible charset conversion)
export client uses ZHS16GBK character set (possible charset conversion)
. importing ZHANGZHONG's objects into SYSTEM
. importing ZHANGZHONG's objects into SYSTEM
. . importing table                         "CITY"        345 rows imported
. . importing table                     "DISTRICT"       2862 rows imported
. . importing table                     "PROVINCE"         34 rows imported
Import terminated successfully without warnings.
```

* 导出数据

> ...


## 参考

* [Docker 本地导入镜像/保存镜像/载入镜像/删除镜像][1]
* [使用DOCKER安装ORACLE 12C DATABASE][2]
* [操作阿里云服务器docker中oracle的一些记录][3]
* [Centos7下利用docker安装oracle12c][4]
* [Docker 拉取 oracle 11g镜像配置][5]
* [Docker中的Oracle数据库][6]
* [Oracle 12c pdb的数据泵导入导出][7]

[1]: https://www.cnblogs.com/linjiqin/p/8604756.html
[2]: http://www.dboracle.com/archivers/oracle-12c-on-docker.html
[3]: https://blog.csdn.net/ys_230014/article/details/84944932
[4]: https://www.jianshu.com/p/83c17111f44d
[5]: https://blog.csdn.net/qq_38380025/article/details/80647620
[6]: https://blog.csdn.net/yidu_fanchen/article/details/75568748
[7]: https://www.cnblogs.com/xqzt/p/5034261.html