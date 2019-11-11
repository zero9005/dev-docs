# MongoDB 备份与恢复

## Mongodump

```shell
> mongodump -h host -d dbname -o dbdirectory
# -h 数据库IP
# -port 端口
# -u 用户名
# -p 密码
# -d 数据库名字
# -c collection的名字
# -o 导出的文件名
# -q 导出数据的过滤条件
# --authenticationDatabase 验证数据库的名称
# --gzip 备份时压缩
```



## mongorestore

```shell
> mongorestore -h <hostname><:port> -d dbname <path>
# --host <:port>, -h<:port> mongodb所在的服务器，默认 localhost:27017
# -h 数据库IP
# -u 用户名
# -p 密码
# -d 数据库名字
# -c collection的名字
# -o 导出的文件名
# -q 导出数据的过滤条件
# --authenticationDatabase 验证数据库的名称
# --gzip 备份时压缩
# --drop 恢复时把之前的集合删掉
```



## mongoexport

> 把一个collection导出为json或csv格式

```shell
> mongoexport -h ${host} --port ${port}  -u ${username} -p ${password} -d ${dbname} -c ${collectionName} -f ${fieldName} -q ${条件} --csv -o ${fileName}
# 条件 ex: -q '{"uid": "100"}'
```



## mongoimport

> 把json/csv导入到collection

```shell
> mongoimport -h ${host:port} -d ${dbname} -c ${collectionName} --drop --headerline <path>
# --headerline  指明第一列是列名，不需要导入
# -j 同时运行插入的操作数(default 1)，并行
```

