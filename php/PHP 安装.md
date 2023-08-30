# PHP 安装

[官网]: https://www.php.net/

## linux

[ 参考 ]: https://blog.csdn.net/mushanshui/article/details/124767064

```shell
>cd php-x.x.x
>./configure --prefix=/usr/local/php --enable-fpm --with-pdo-mysql --with-mysqli --without-sqlite3 --with-curl --with-openssl --with-zlib --with-zlib-dir=../zlib-1.2.11
```

-  error: Package requirements (libxml-2.0 >= 2.9.0) were not met:

```shell
>sudo apt install libxml2-dev
```

- Package requirements (sqlite3 >= 3.7.7) were not met:

```shell
>sudo apt install libsqlite3-dev
```

- Package requirements (libcurl >= 7.29.0) were not met:

```shell
>sudo apt install libcurl4-openssl-dev 
```

