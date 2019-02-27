[TOC]
# 目录结构
## conf 配置文件
## data 数据库内容
## log 数据日志

## init
初始化数据库脚本
增加 su ，并修改权限，可以根据业务增加
```
# 大于 等于8.0
create user 'su'@'%' identified by '123456';
grant all privileges on *.* to 'su'@'%' identified by '123456';
```

# 运行命令
1. 创建并运行容器
```
docker-compose up -d
docker-compose up 
```
2. 停止
```
docker-compose stop redis

```
3. 删除容器
```
docker-compose rm redis

```
