# ElasticSearch的安装使用

## 1、安装

> 访问<a href=' https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html'>官网</a>

```shell
> curl -L -O xxx/elasticsearch-x.y.z-linux-x86_64.tar.gz
> tar -xzvf elasticsearch-x.y.z-linux-x86_64.tar.gz
> sudo mv elasticsearch-x.y.z /opt/
```



## 2、启动

```shell
> ./bin/elasticsearch -d
```



## 3、设置

- 设置启动IP

  > 默认绑定的是 localhost, 即外网不可访问

  ```shell
  > sudo vi ./conf/elasticsearch.yml
  #network.host: 0.0.0.0
  ```

  



## 4、启动问题

>  max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]

最大虚拟内存值为65530，属于过低，需要调整到最少262144

```shell
> sudo vi /etc/sysctl.conf
# vm.max_map_count=262144
# sysctl -p
```



> the default discovery settings are unsuitable for production use; at least one of [discovery.seed_hosts, discovery.seed_providers, cluster.initial_master_nodes] must be configured

```shell
> sudo vi ./confg/elasticsearch.yml
# cluster.initial_master_nodes: ["node-1"]
```



## 5、分析器

```shell
> curl -x GET "http://localhost:9200/_analyze" -d '{
	'anaylyzer': 'ik_max_word' # ik_smart
	'text': 'search text'
}'
```

