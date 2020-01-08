# Ubuntu 18.0.4 apt 安装MySQL5.7

## 1、安装步骤

```shell
> sudo apt install mysql-server-5.7
```



## 2、更改配置

```shell
> sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
#bind-address = 127.0.0.1
```



## 3、获得初始账号密码

```shell
> sudo cat /etc/mysql/debian.cnf
```



## 4、更改root密码

``` shell
> mysql -u debian-sys-maint -p
> use mysql
> update user set authentication_string=PASSWORD("root的密码") where user='root';
> update user set plugin='mysql_native_password' where user='root';
> flush privileges;
> exit;
> sudo service mysql restart
```

