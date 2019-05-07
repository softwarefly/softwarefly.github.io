---
layout: post
title: Import and Export Databases in MySQL Docker Container
categories: Deployment
description: Import and Export Databases in MySQL Docker Container
keywords: Docker, MySQL
---

## 导入数据

```sh
$ docker exec -it mysqltest2 bash
root@28ddb46a15b8:/#
root@28ddb46a15b8:/# mysql -uroot -p123456
mysql> select host,user,plugin,authentication_string from mysql.user;
mysql> ALTER user 'root'@'%' IDENTIFIED WITH mysql_native_password BY '123456';(自己修改数据库密码)
mysql> FLUSH PRIVILEGES;

#copy data to /docker/mysql/data/
root@28ddb46a15b8:/# mysql -uroot -p < employees.sql
```

<div align=left>
<img src = "/images/posts/deployment/mysql-import.jpg" width = "600"/>
</div>

## 导入导出命令

```sh
# Backup
docker exec CONTAINER /usr/bin/mysqldump -u root --password=root DATABASE > backup.sql

# Restore
cat backup.sql | docker exec -i CONTAINER /usr/bin/mysql -u root --password=root DATABASE
```

```sh
docker exec -i mysql_container mysql -uroot -psecret mysql < db.sql
docker exec -i container_name mysql -uroot dbname < data.sql;
```

## Reference

* [Mysql数据库迁移：善用Navicat工具，事半功倍][1]

[1]: https://blog.csdn.net/wd2014610/article/details/81487004