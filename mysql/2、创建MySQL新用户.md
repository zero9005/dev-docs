# 2、创建MySQL新用户



## 使用root登录

```shell
> mysql -uroot -p
```



## 创建用户

```shell
> create user 'username'@'%' identified by 'password';
# @'%' % 泛指所有ip
```



## 授权权限

```shell
> grant all privileges on *.* to 'username'@'%';
# *.* dbname.tablename
# @'%' % 泛指所有ip

# all privileges
# create
# drop
# delete
# insert
# select
# update
# grant option
```



## 刷新权限缓存

```shell
> flush privileges;
```



## 查看当前用户的grants

```shell
> mysql -u ${username} -p

> show grants;
```



## 撤销用户权限

```shell
> revoke type_of_permission on database.table_name from 'username'@'%';
```

