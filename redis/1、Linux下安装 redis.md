# 1、Linux下安装 redis

## 编译安装

```shell
> wget ${redis-downloadUrl}
> tar -zxvf redis-x.tar.gz
> cd redis-x
> make
> cd src
> sudo make install PREFIX=/opt/redis
> sudo cp ~/redis-x/redis.conf /opt/redis
> vi /opt/redis/redis.conf
# password
# daemonize
```

## 设置开机启动

```shell
> vi /etc/rc.local
# /opt/redis/bin/redis-server /opt/redis/redis.conf
```



## 常用命令

- 启动

  > ./bin/redis-server .redis.conf

- 停止

  > pkill redis