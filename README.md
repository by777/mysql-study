# 视频地址
[B站链接](https://www.bilibili.com/video/BV1NJ411J79W)

# MYSQL 5.7 
https://cdn.mysql.com//archives/mysql-5.7/mysql-5.7.19-winx64.zip

新建my.ini
```ini
[mysqld]
basedir=E:\mysql-5.7.19-winx64\
datadir=E:\mysql-5.7.19-winx64\data\
port=3306
skip-grant-tables
```
进入mysql\bin目录执行
```cmd
mysqld -install
# Service successfully installed.
mysqld --initialize-insecure --user=mysql
# 初始化data目录
net start mysql
# 启动mysql服务
mysql -u root -p
update mysql.user set authentication_string=password('123456') where user='root' and Host='localhost';
flush privileges;
```
删除my.ini最后一行skip-grant-tables，重启MySQL
```cmd
net stop mysql
net start mysql
#sc delete mysql 清空服务
```
# SQLyog安装
https://blog.csdn.net/lihua5419/article/details/73881837/

# P5 命令行基本操作
    mysql -u root -p

```sql
select * from mysql.user;
# 修改用户密码
update mysql.user set authentication_string=password('123456') where `User`='root' and `Host`='localhost';
# 刷新权限
flush privileges;

-----------------
# 查看所有数据库
show databases;

# 使用数据库
use mysql;

# 查看所有的表
show tables;

# 查看表结构
descibe users; # 或者desc 

# 创建一个数据库
create database westos;
```