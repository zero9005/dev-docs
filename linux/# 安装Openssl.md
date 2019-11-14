# 安装Openssl

## 下载

> 访问<a href=" https://www.openssl.org/ ">官网</a>

``` shell
> wget https://www.openssl.org/source/openssl-1.1.1d.tar.gz
> tar -zxvf openssl-1.1.1d.tar.gz 
> cd openssl-1.1.1d
> ./config
> make
> sudo make install
> sudo mv /usr/bin/openssl /usr/bin/openssl.bak
> sudo ln -s /usr/local/bin/openssl /usr/bin/openssl
> sudo ln -s /usr/local/include/openssl /usr/include/openssl
> su root
> echo "/usr/local/lib" >> /etc/ld.so.conf
```



## test

```shell
> openssl version
```

> openssl: error while loading shared libraries: libssl.so.1.1: cannot open shared object file: No such file or directory

```shell
> sudo ln -s /usr/local/lib/libssl.so.1.1 /usr/lib/libssl.so.1.1
> sudo ln -s /usr/local/lib/libcrypto.so.1.1 /usr/lib/libcrypto.so.1.1
```

