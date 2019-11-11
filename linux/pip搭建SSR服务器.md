# pip搭建SSR服务器

```shell
> apt-get install python-pip
> pip install --upgrade pip
```



>  No module named setuptools 

```shell
> sudo apt-get install -y python-setuptools
```

```shell
pip install shadowsocks
```



> undefined symbol: EVP_CIPHER_CTX_cleanup

```shell
> vi /usr/local/lib/python2.7/dist-packages/shadowsocks/crypto/openssl.py
# cleanup 替换为 reset
```



## 配置

```shell
> vi ssr_config.json
{
	"server":"ip",
	"server_port": 8388,
	"local_port": 8020,
	"password": "${password}",
	"timeout": 600,
	"method": "aes-256-cfb"
}
```





## 启动

``` shell
ssserver -c ssr_config.json -d start
```

