# 1、Linux下安装 nginx

> 需要提前准备 pcre, zlib



> 安装openssl依赖

```shell
> sudo apt install libssl-dev
```

```shell
> tar -xzvf nginx-x.tar.gz
> cd nginx-x
> ./configure --prefix=/opt/nginx --with-http_ssl_module --with-pcre=../pcre-8.41 --with-zlib=../zlib-1.2.11
```

